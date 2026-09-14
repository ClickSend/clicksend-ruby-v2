# Migration Guide: clicksend_client (legacy) → clicksend (v2)

This guide helps you migrate from the legacy ClickSend Ruby SDK (`clicksend_client`, module `ClickSendClient`) to the current v2 SDK (`clicksend`, module `ClickSend`). The two gems are **not drop-in compatible** — the gem name, module name, require path, method names, request/response shapes, and a large chunk of the API surface have all changed. Read this guide fully before upgrading, then use the class/method mapping tables to update your code.

## Contents

1. [Why this migration isn't a drop-in replacement](#1-why-this-migration-isnt-a-drop-in-replacement)
2. [Installation & imports](#2-installation--imports)
3. [Authentication & client setup](#3-authentication--client-setup)
4. [Base path / URL changes](#4-base-path--url-changes)
5. [Method naming convention change](#5-method-naming-convention-change)
6. [Request payloads: `*Request` models replace reusable domain models](#6-request-payloads-request-models-replace-reusable-domain-models)
7. [Response payloads are now properly typed](#7-response-payloads-are-now-properly-typed)
8. [Error handling changes](#8-error-handling-changes)
9. [No async request mode in either version — plus per-call request controls](#9-no-async-request-mode-in-either-version--plus-per-call-request-controls)
10. [Class-by-class mapping (all 37 legacy classes)](#10-class-by-class-mapping-all-37-legacy-classes)
11. [Side-by-side examples for common operations](#11-side-by-side-examples-for-common-operations)
12. [The Voice naming trap (read this before touching voice code)](#12-the-voice-naming-trap-read-this-before-touching-voice-code)
13. [Endpoints/methods removed in v2](#13-endpointsmethods-removed-in-v2)
14. [Brand-new resources and methods in v2](#14-brand-new-resources-and-methods-in-v2)
15. [Step-by-step migration checklist](#15-step-by-step-migration-checklist)

## 1. Why this migration isn't a drop-in replacement

The legacy SDK grew organically against ClickSend's v3 API: one API class per rough "concept" (e.g. `TransactionalEmailApi`, `EmailMarketingApi`, `MasterEmailTemplatesApi`, `UserEmailTemplatesApi`, `EmailDeliveryReceiptRulesApi` were five *separate* classes), method names followed a `resource_path` + HTTP verb pattern (`sms_send_post`, `sms_history_get`), request bodies were broad reusable domain models (`SmsMessage`, `SmsMessageCollection`), and every response body was declared `return_type => 'String'` and never deserialized.

The v2 SDK is generated fresh from ClickSend's current OpenAPI v3 specification for Ruby, which:

- Groups methods into **one class per resource/tag** (26 classes instead of 37 — several legacy classes were merged, one was split, and the Fax, Letters, and Postcards classes were dropped entirely — see [§13](#13-endpointsmethods-removed-in-v2)).
- Names methods after the endpoint's **operationId** (`send_sms`, `view_sms_history`, `export_sms_history`) instead of `resource` + verb.
- Wraps every request body in a dedicated, single-purpose `*Request` model instead of reusing broad domain models — the `models/` folder went from 47 files to 383.
- Deserializes every response into a specific per-operation model class (subclassing a shared `ApiModelBase`) with real accessor methods, instead of handing back a raw JSON string.
- Renames the top-level module from **`ClickSendClient` to `ClickSend`** — this changes *every* namespaced reference in your code, e.g. `ClickSendClient::SMSApi` → `ClickSend::SmsApi`.
- Keeps `ApiError` as the exception class and `typhoeus` as the HTTP backend, but slims the runtime dependency list (drops the legacy's `json` and `addressable` gem dependencies) and adds a friendlier `ApiError#message`/`#to_s`.
- Adds `Configuration` options for multi-server specs (`server_index`, `server_operation_index`, `server_variables`), a dynamic bearer-token getter (`access_token_getter`), and raw-binary response mode (`return_binary_data`).

None of this changes the underlying REST API — it's the same ClickSend v3 API — but it does change **every call site** in your existing integration.

## 2. Installation & imports

| | Legacy | v2 |
|---|---|---|
| Gem name | `clicksend_client` | `clicksend` |
| Version at time of writing | `5.1.4` | `6.0.2` |
| Ruby module | `ClickSendClient` | `ClickSend` |
| Require statement | `require 'clicksend_client'` | `require 'clicksend'` |
| Ruby version required | `>= 2.7` (gemspec) | `>= 2.7` (gemspec) — unchanged |
| Runtime deps | `typhoeus ~> 1.4`, `json ~> 2.7`, `addressable ~> 2.8` | `typhoeus ~> 1.0` only |
| Response validation | none (`String`) | typed model objects, deserialized per operation |

```ruby
# Gemfile — before
gem 'clicksend_client', '~> 1.0.0'

# Gemfile — after
gem 'clicksend', git: 'https://github.com/ClickSend/clicksend-ruby-v2.git'
```

Because the gem name itself changes, `bundle update` alone won't do it — remove `clicksend_client`, add `clicksend`, run `bundle install`, then update every `ClickSendClient::` reference in your code to `ClickSend::`:

```ruby
# Legacy
require 'clicksend_client'
ClickSendClient.configure { |c| ... }
ClickSendClient::SMSApi.new

# v2
require 'clicksend'
ClickSend.configure { |c| ... }
ClickSend::SmsApi.new
```

The v2 gem is not (yet) published as a versioned release on RubyGems in the sources reviewed for this guide — install it straight from GitHub via the `git:` Gemfile option shown above, or vendor it locally. Confirm the current distribution channel for your account before changing a `Gemfile.lock` in production.

## 3. Authentication & client setup

Authentication itself is unchanged — both SDKs use HTTP Basic Auth with your ClickSend **username** and **API key**, configured through a `configure` block:

```ruby
# Legacy
ClickSendClient.configure do |config|
  config.username = ENV['CLICKSEND_USERNAME']
  config.password = ENV['CLICKSEND_API_KEY']
end

api_instance = ClickSendClient::SMSApi.new

# v2
ClickSend.configure do |config|
  config.username = ENV['CLICKSEND_USERNAME']
  config.password = ENV['CLICKSEND_API_KEY']
end

api_instance = ClickSend::SmsApi.new
```

`Configuration` gained several attributes in v2 that don't exist in the legacy gem. You don't need to set any of these, but they're available if you need them:

| New in v2 `Configuration` | Purpose |
|---|---|
| `server_index` / `server_operation_index` | Select between multiple declared API servers, globally or per-operation |
| `server_variables` / `server_operation_variables` | Template variables for the above |
| `access_token_getter` | A `Proc` that dynamically returns a bearer token, overriding a static `access_token` |
| `return_binary_data` | Return raw binary response bodies instead of attempting deserialization |
| `ignore_operation_servers` | Force the global server config even when an operation declares its own |

If your code only ever sets `.username` / `.password` inside a `configure` block, the **only required change is the module rename** (`ClickSendClient` → `ClickSend`) plus renaming the `*Api` class you instantiate (see [§10](#10-class-by-class-mapping-all-37-legacy-classes)).

## 4. Base path / URL changes

| | Legacy | v2 |
|---|---|---|
| Default `host` | `rest.clicksend.com` | `rest.clicksend.com` (unchanged) |
| Default `base_path` | `/v3` | `''` (empty string) |
| Per-method resource path | `/sms/send` (relative to `base_path`) | `/v3/sms/send` (the `/v3` prefix is now baked into each method's path) |

The final resolved URL is identical in both cases (`https://rest.clicksend.com/v3/sms/send`). This only matters if you've overridden `config.base_path` or `config.host` — e.g. to point at a proxy or mock server. If your custom `base_path` currently ends in `/v3` for the legacy SDK, **remove that suffix** when you switch to v2, or you'll end up requesting `.../v3/v3/sms/send`.

## 5. Method naming convention change

Every method on every API class has been renamed. There is no shared prefix/suffix rule you can find-and-replace — the new names follow each endpoint's `operationId` (snake_cased), which reads like an English phrase, while the old ones followed `resource_path` + HTTP verb.

| Legacy | v2 |
|---|---|
| `sms_send_post` | `send_sms` |
| `sms_history_get` | `view_sms_history` |
| `sms_history_export_get` | `export_sms_history` |
| `sms_templates_by_template_id_delete` | `delete_sms_template` |
| `lists_contacts_by_list_id_post` | `create_new_contact` |
| `subaccounts_post` | `create_subaccount` |
| `voice_lang_get` | `view_voice_languages` |
| `numbers_search_by_country_get` | `view_available_numbers` |

**You cannot mechanically derive the new name from the old one.** Use the mapping tables in [§10](#10-class-by-class-mapping-all-37-legacy-classes)–[§11](#11-side-by-side-examples-for-common-operations), or open the relevant `*Api` class source (or its page under `docs/` in the v2 repo) to find the right method.

Every generated method — in both versions — also exposes a `..._with_http_info` variant that returns `[data, status_code, headers]` instead of just `data`. That pattern is unchanged between versions.

## 6. Request payloads: `*Request` models replace reusable domain models

Legacy methods took a broad, reusable domain model as a **positional argument**, with an optional `opts` hash for query parameters:

```ruby
# Legacy
sms_message = ClickSendClient::SmsMessage.new(
  to: '+61411111111',
  from: '',
  body: 'Hello from ClickSend Ruby SDK!',
  source: 'ruby'
)
collection = ClickSendClient::SmsMessageCollection.new(messages: [sms_message])

api_instance.sms_send_post(collection)
```

v2 introduces **one dedicated `*Request` model per operation**, passed as a **named key inside the `opts` hash** — there is no positional request-body argument any more:

```ruby
# v2
send_sms_request = ClickSend::SendSmsRequest.new(
  messages: [
    { to: '+61411111111', body: 'Hello from ClickSend!', source: 'sdk' }
  ]
)

api_instance.send_sms(send_sms_request: send_sms_request)
```

For methods that also take a path parameter (an ID in the URL), that ID stays a leading **positional** argument, and only the request body moves into `opts`:

```ruby
# Legacy — template model positional, template_id positional
api_instance.sms_templates_by_template_id_put(template_id, sms_template, opts = {})

# v2 — template_id stays positional; the request body is a named opts key
api_instance.update_sms_template(template_id, create_sms_template_request: request_body)
```

Practical implications:

- **The old domain-model class names mostly don't exist in v2.** `SmsMessage`, `SmsMessageCollection`, `Email`, `Voice`, `ContactList`, `Subaccount`, etc. are gone. The `models/` folder went from 47 files to 383, almost all named after a specific operation (`send_sms_request.rb`, `create_new_contact_request.rb`, `create_subaccount_request.rb`, …) rather than a domain noun. Nested list items get their own generated models too (e.g. `SendSmsRequestMessagesInner`).
- **There is no 1:1 old-model-to-new-model mapping.** When migrating a call site, open the corresponding page under `docs/` in the v2 repo (e.g. `docs/SendSmsRequest.md`) to see the exact fields the new request model expects, rather than assuming the old model's shape still applies.
- **Watch for asymmetric request-model reuse on updates.** v2 doesn't always generate a separate `Update*Request` model — e.g. `SmsApi#update_sms_template` takes a `create_sms_template_request:` key (there is no `UpdateSmsTemplateRequest` model at all), even though its *response* type is `UpdateSmsTemplate`. Check each method's actual `@option opts` documentation rather than guessing the request-model name from the method name.
- **The sender field is simply `from` in both versions.** Ruby has no keyword-collision issue with `from` (unlike Python's `_from`/`var_from` workaround), so `ClickSendClient::SmsMessage#from` and `ClickSend::SendSmsRequestMessagesInner#from` are both plain attributes — no aliasing needed.
- `source` now defaults to **`'sdk-ruby'`** on SMS, MMS, and voice message items if you don't set it explicitly (confirmed in `send_sms_request_messages_inner.rb`, `send_mms_request_messages_inner.rb`, and `send_voice_message_request_messages_inner.rb`). The legacy SDK had no default for `source`.
- Every v2 method also accepts an optional `content_type:` key in `opts` for the `Content-Type` header; you can omit it — it defaults to `application/json`.

## 7. Response payloads are now properly typed

This is the change most likely to break existing code silently.

**In the legacy SDK, every API method returned a raw JSON string.** The generated code declared `return_type => 'String'` for every operation:

```ruby
# Legacy
response = api_instance.sms_send_post(collection)
# response is a String like:
# '{"http_code":200,"response_code":"SUCCESS","data":{"messages":[...]}}'

parsed = JSON.parse(response)
status = parsed['data']['messages'][0]['status']
```

**In v2, every API method deserializes the response into a typed model object** with real accessor methods:

```ruby
# v2
result = api_instance.send_sms(send_sms_request: send_sms_request)
# result is a ClickSend::SendSms instance

status = result.data.messages.first.status
```

Action required: search your codebase for `JSON.parse` calls on the result of any ClickSend API call, and any manual hash-key access (`result['data']`, `result[:data]`, etc.) on those results. Model classes don't respond to `[]` the way a `Hash` does, so this raises `NoMethodError` under v2 — rewrite it as attribute access (`result.data`). Every model class also exposes `to_hash` and `to_body` if you need a plain `Hash` for logging or serialization.

To get the status code and headers alongside the body, use the `*_with_http_info` variant of any method — this returns `[data, status_code, headers]` in both SDKs, so that part of your code doesn't need to change.

## 8. Error handling changes

Both SDKs raise `ApiError` on non-2xx responses, and the core attributes are unchanged — only the **namespace** and the **error message formatting** differ. Unlike some other ClickSend SDKs' v2 (e.g. Python's status-specific `BadRequestException`/`NotFoundException` subclasses), **Ruby v2 does not add subclasses** — it's still a single `ApiError` class in both versions.

| | Legacy | v2 |
|---|---|---|
| Class | `ClickSendClient::ApiError` | `ClickSend::ApiError` |
| Base class | `StandardError` | `StandardError` |
| Attributes | `.code`, `.response_headers`, `.response_body` | `.code`, `.response_headers`, `.response_body` (unchanged) |
| `#message` / `#to_s` | Default `StandardError` behavior (whatever string was passed to `.new`) | Overridden to compose a multi-line, human-readable message from `code` + `response_headers` + `response_body` |
| Subclasses | none | none |

```ruby
# Legacy
begin
  api_instance.sms_send_post(collection)
rescue ClickSendClient::ApiError => e
  puts "#{e.code}: #{e.response_body}"
end

# v2
begin
  api_instance.send_sms(send_sms_request: send_sms_request)
rescue ClickSend::ApiError => e
  puts e.message
  # Error message: the server returns an error
  # HTTP status code: 400
  # Response headers: {...}
  # Response body: {...}
end
```

**Audit every `rescue ClickSendClient::ApiError` block** — fix the namespace (`ClickSend::ApiError`), and note that a bare `rescue ClickSendClient::ApiError` will no longer catch anything from v2. If your existing block manually stitched together `code` / `response_body` into a log line, you can likely simplify it to just `e.message` under v2.

## 9. No async request mode in either version — plus per-call request controls

**Unlike ClickSend's Python/Java SDKs, neither the legacy Ruby SDK nor v2 ever had an `async_req`-style thread-pool execution mode.** Both versions are synchronous, single-request-per-call, built on `typhoeus`. There is nothing to remove here and nothing new to adopt — if you need concurrency, you always had to (and still have to) build it yourself, e.g. with `Thread` / `Concurrent::Promise` / a thread pool, giving each worker its own `ApiClient` instance since `ApiClient.default` is a shared, mutable singleton.

What *is* available in both versions, unchanged, is a set of **per-call `opts` overrides** that every generated method accepts and passes straight through to `call_api`:

| `opts` key | Purpose |
|---|---|
| `header_params: {...}` | Extra/override headers for this one call |
| `query_params: {...}` | Extra/override query parameters |
| `form_params: {...}` | Extra/override form fields |

Client-wide options remain on `Configuration`: `config.timeout = 30` for a request timeout (seconds; `0` means never time out, the default in both versions). The `User-Agent` isn't a `Configuration` attribute in either version — it lives on the `ApiClient` instance instead, defaulting to `ClickSend-Codegen/5.1.4/ruby` (legacy) vs. `ClickSend-SDK/6.0.2/ruby` (v2), and overridable via `api_client.user_agent = "..."`.

## 10. Class-by-class mapping (all 37 legacy classes)

26 v2 classes now cover what used to be 37 legacy classes. Some legacy classes merged (five email classes → one `EmailApi`); the Fax, Letters, and Postcards classes were **dropped entirely** (see [§13](#13-endpointsmethods-removed-in-v2)); and — critically — the two Voice classes **swapped roles** in v2 naming (see [§12](#12-the-voice-naming-trap-read-this-before-touching-voice-code)).

| Legacy class | → | New class(es) | Notes |
|---|---|---|---|
| `AccountApi` | → | `ManagementApi`, `VerificationApi` | Split: `account_get`/`account_useage_by_subaccount_get` → `ManagementApi`; `forgot_password_put`/`forgot_username_put` → `VerificationApi`. Four methods have no v2 equivalent — see [§13](#13-endpointsmethods-removed-in-v2). |
| `AccountRechargeApi` | → | `TransactionsApi` | Renamed 1:1 (6 methods). |
| `ContactApi` | → | `ContactsApi`, `ListsApi` | Split: single-contact-by-id CRUD (`get_specific_contact`/`update_contact`/`delete_contact`) → `ContactsApi`; list-scoped contact ops (create/list/copy/transfer/remove-opted-out) → `ListsApi`. |
| `ContactListApi` | → | `ListsApi` | Merged into `ListsApi`. |
| `CountriesApi` | → | `InternationalMessagingApi` | `countries_get` → `list_countries`. |
| `DeliveryIssuesApi` | → | `MessageDeliveryApi` | Renamed. Unrelated to the delivery-*receipt-rule* classes despite the similar name. |
| `DetectAddressApi` | → | _(removed)_ | Address detection/parsing has no v2 equivalent — see [§13](#13-endpointsmethods-removed-in-v2). |
| `EmailDeliveryReceiptRulesApi` | → | `EmailApi` | Folded into the unified `EmailApi`. |
| `EmailMarketingApi` | → | `EmailApi` | Folded into the unified `EmailApi`. |
| `EmailToSmsApi` | → | `EmailToSmsApi` | Same class name, methods renamed (7 → 7). |
| `FaxApi` | → | _(removed)_ | Fax is not part of the v2 SDK — see [§13](#13-endpointsmethods-removed-in-v2). |
| `FaxDeliveryReceiptRulesApi` | → | _(removed)_ | Fax is not part of the v2 SDK — see [§13](#13-endpointsmethods-removed-in-v2). |
| `GlobalSendingApi` | → | `InternationalMessagingApi` | Folded in (`user_countries_get`/`_post`/`_agree_post` → `view_countries`/`select_countries_for_global_sending`/`agree_to_rules_and_regulation`; `list_countries_get` → `get_countries_for_global_sending`). |
| `InboundFaxRulesApi` | → | _(removed)_ | Fax is not part of the v2 SDK — see [§13](#13-endpointsmethods-removed-in-v2). |
| `InboundSmsRulesApi` | → | `SmsApi` | Folded in as `*_sms_inbound_automation(s)`. |
| `MMSApi` | → | `MmsApi` | Renamed 1:1 for 4 methods; 2 dropped — see [§13](#13-endpointsmethods-removed-in-v2). |
| `MasterEmailTemplatesApi` | → | `EmailApi` | Folded into the unified `EmailApi`. |
| `MmsCampaignApi` | → | `MmsCampaignsApi` | Renamed (plural), 6 methods. |
| `NumberApi` | → | `NumbersApi` | Renamed 1:1 (3 methods), plus a brand-new `register_numbers` — see [§14](#14-brand-new-resources-and-methods-in-v2). |
| `PostLetterApi` | → | _(removed)_ | Letters is not part of the v2 SDK — see [§13](#13-endpointsmethods-removed-in-v2). |
| `PostPostcardApi` | → | _(removed)_ | Postcards is not part of the v2 SDK — see [§13](#13-endpointsmethods-removed-in-v2). |
| `PostReturnAddressApi` | → | `AddressesApi` | Renamed (5 methods): `post_return_addresses_*` → `*_return_address(es)`. |
| `ReferralAccountApi` | → | `ReferralsApi` | `referral_accounts_get` → `view_referral_accounts`. |
| `ResellerAccountApi` | → | `ResellerApi` | Merged with `TransferCreditApi`'s reseller-transfer method. |
| `SMSApi` | → | `SmsApi` | Renamed 1:1 for all core methods. |
| `SMSDeliveryReceiptRulesApi` | → | `SmsApi` | Folded in as `*_sms_delivery_receipt_rule(s)`. |
| `SearchApi` | → | `ListsApi` | `search_contacts_lists_get` → `view_contact_lists`. **Not removed** — verified present on `ListsApi` in the generated v2 SDK. |
| `SmsCampaignApi` | → | `SmsCampaignsApi` | Renamed (plural), 6 methods. |
| `StatisticsApi` | → | `StatisticsApi` | Same class name: `statistics_sms_get` → `view_sms_statistics`, `statistics_voice_get` → `view_voice_statistics`. |
| `SubaccountApi` | → | `SubaccountsApi` | Renamed (plural), 6 methods. |
| `TimezonesApi` | → | `InternationalMessagingApi` | `timezones_get` → `timezones`. |
| `TransactionalEmailApi` | → | `EmailApi` | Folded into the unified `EmailApi`. |
| `TransferCreditApi` | → | `TransactionsApi` (account recharge transfer) / `ResellerApi` (reseller transfer) | `TransferCreditApi` only ever had one method, `reseller_transfer_credit_put`, which maps to `ResellerApi#reseller_transfer_credit`. |
| `UploadApi` | → | `UploadsApi` | `uploads_post` → `upload_a_media_file`. |
| `UserEmailTemplatesApi` | → | `EmailApi` | Folded into the unified `EmailApi`. |
| `VoiceApi` (send/history/price/lang) | → | **`VoiceMessagingApi`** | ⚠️ See [§12](#12-the-voice-naming-trap-read-this-before-touching-voice-code) — this is *not* the new `VoiceApi`. 2 methods dropped — see [§13](#13-endpointsmethods-removed-in-v2). |
| `VoiceDeliveryReceiptRulesApi` | → | **`VoiceApi`** | ⚠️ See [§12](#12-the-voice-naming-trap-read-this-before-touching-voice-code) — the new `VoiceApi` only has delivery-receipt-rule methods. |

`AlphaTagsApi`, `DefaultSendersApi`, `OwnNumbersApi`, and `UrlShorteningApi` in v2 have **no legacy predecessor at all** — see [§14](#14-brand-new-resources-and-methods-in-v2). Note in particular that `OwnNumbersApi` is **not** a split-off of `NumberApi` (the legacy SDK never had a "manage your own numbers" concept) — `NumberApi` maps cleanly 1:1 onto `NumbersApi`, and `OwnNumbersApi` is entirely new functionality.

### Email: the five legacy classes → `EmailApi`

| Legacy | v2 (`EmailApi`) |
|---|---|
| `TransactionalEmailApi#email_send_post` | `send_email` |
| `TransactionalEmailApi#email_history_get` | `view_email_history` |
| `TransactionalEmailApi#email_history_export_get` | `export_email_history` |
| `TransactionalEmailApi#email_price_post` | `calculate_email_price` |
| `EmailMarketingApi#email_campaign_post` | `send_email_campaign` |
| `EmailMarketingApi#email_campaigns_get` | `view_all_email_campaigns` |
| `EmailMarketingApi#email_campaign_get` | `view_email_campaign` |
| `EmailMarketingApi#email_campaign_put` | `update_email_campaign` |
| `EmailMarketingApi#cancel_email_campaign_put` | `cancel_email_campaign` |
| `EmailMarketingApi#email_campaign_price_post` | `calculate_email_campaign_price` |
| `EmailMarketingApi#email_campaign_history_get` | `view_email_campaign_history` |
| `EmailMarketingApi#email_campaign_history_export_get` | `export_email_campaign_history` |
| `EmailMarketingApi#allowed_email_address_get` | `view_allowed_email_addresses` |
| `EmailMarketingApi#allowed_email_address_post` | `create_allowed_email_address` |
| `EmailMarketingApi#specific_allowed_email_address_get` | `view_allowed_email_address` |
| `EmailMarketingApi#specific_allowed_email_address_delete` | `delete_allowed_email_address` |
| `EmailMarketingApi#verify_allowed_email_address_get` | `verify_allowed_email_address` |
| `EmailMarketingApi#send_verification_token_get` | `send_email_verification_token` |
| `UserEmailTemplatesApi#email_templates_get` | `view_email_templates` |
| `UserEmailTemplatesApi#email_template_get` | `view_email_template` |
| `UserEmailTemplatesApi#email_template_post` | `create_email_template` |
| `UserEmailTemplatesApi#email_template_put` | `update_email_template` |
| `UserEmailTemplatesApi#email_template_delete` | `delete_email_template` |
| `MasterEmailTemplatesApi#master_email_templates_get` | `view_master_email_templates` |
| `MasterEmailTemplatesApi#master_email_template_get` | `view_master_email_template` |
| `MasterEmailTemplatesApi#master_email_template_categories_get` | `view_template_categories` |
| `MasterEmailTemplatesApi#master_email_template_category_get` | `view_template_category` |
| `MasterEmailTemplatesApi#master_email_templates_in_category_get` | `view_templates_in_category` |
| `EmailDeliveryReceiptRulesApi#email_delivery_receipt_automations_get` | `view_email_delivery_receipt_rules` |
| `EmailDeliveryReceiptRulesApi#email_delivery_receipt_automation_get` | `view_email_delivery_receipt_rule` |
| `EmailDeliveryReceiptRulesApi#email_delivery_receipt_automation_post` | `create_email_delivery_receipt_rule` |
| `EmailDeliveryReceiptRulesApi#email_delivery_receipt_automation_put` | `update_email_delivery_receipt_rule` |
| `EmailDeliveryReceiptRulesApi#email_delivery_receipt_automation_delete` | `delete_email_delivery_receipt_rule` |

> `EmailMarketingApi#email_campaign_put` in the legacy SDK reused an `EmailCampaign` model for update; v2's `update_email_campaign` takes an `update_email_campaign_request:` opts key. Same story for every other method above — always check the current `@option opts` doc comment on the method rather than assuming the old model's shape carries over.

### SMS: `SMSApi` + `InboundSmsRulesApi` + `SMSDeliveryReceiptRulesApi` → `SmsApi`

| Legacy | v2 (`SmsApi`) |
|---|---|
| `SMSApi#sms_send_post` | `send_sms` |
| `SMSApi#sms_history_get` | `view_sms_history` |
| `SMSApi#sms_history_export_get` | `export_sms_history` |
| `SMSApi#sms_price_post` | `calculate_sms_price` |
| `SMSApi#sms_cancel_all_put` | `cancel_all_sms` |
| `SMSApi#sms_cancel_by_message_id_put` | `cancel_sms` |
| `SMSApi#sms_inbound_get` | `view_inbound_sms` |
| `SMSApi#sms_inbound_post` | `create_test_inbound_sms` |
| `SMSApi#sms_inbound_read_put` | `mark_inbound_sms_as_read` |
| `SMSApi#sms_inbound_read_by_message_id_put` | `mark_specific_inbound_sms_message_as_read` |
| `SMSApi#sms_receipts_get` | `view_sms_receipts` |
| `SMSApi#sms_receipts_by_message_id_get` | `view_specific_sms_receipt` |
| `SMSApi#sms_receipts_post` | `create_test_sms_receipt` |
| `SMSApi#sms_receipts_read_put` | `mark_sms_receipt_as_read` |
| `SMSApi#sms_templates_get` | `view_sms_templates` |
| `SMSApi#sms_templates_post` | `create_sms_template` |
| `SMSApi#sms_templates_by_template_id_put` | `update_sms_template` |
| `SMSApi#sms_templates_by_template_id_delete` | `delete_sms_template` |
| `InboundSmsRulesApi#sms_inbound_automations_get` | `view_sms_inbound_automations` |
| `InboundSmsRulesApi#sms_inbound_automation_get` | `view_sms_inbound_automation` |
| `InboundSmsRulesApi#sms_inbound_automation_post` | `create_sms_inbound_automation` |
| `InboundSmsRulesApi#sms_inbound_automation_put` | `update_sms_inbound_automation` |
| `InboundSmsRulesApi#sms_inbound_automation_delete` | `delete_sms_inbound_automation` |
| `SMSDeliveryReceiptRulesApi#sms_delivery_receipt_automations_get` | `view_sms_delivery_receipt_rules` |
| `SMSDeliveryReceiptRulesApi#sms_delivery_receipt_automation_get` | `view_sms_delivery_receipt_rule` |
| `SMSDeliveryReceiptRulesApi#sms_delivery_receipt_automation_post` | `create_sms_delivery_receipt_rule` |
| `SMSDeliveryReceiptRulesApi#sms_delivery_receipt_automation_put` | `update_sms_delivery_receipt_rule` |
| `SMSDeliveryReceiptRulesApi#sms_delivery_receipt_automation_delete` | `delete_sms_delivery_receipt_rule` |
| — | `view_a_specific_sms_template` *(new — see [§14](#14-brand-new-resources-and-methods-in-v2))* |
| — | `view_a_specific_inbound_sms_message` *(new — see [§14](#14-brand-new-resources-and-methods-in-v2))* |

### Contacts & lists: `ContactApi` + `ContactListApi` + `SearchApi` → `ContactsApi` + `ListsApi`

| Legacy | v2 |
|---|---|
| `ContactApi#lists_contacts_by_list_id_and_contact_id_get` | `ContactsApi#get_specific_contact` |
| `ContactApi#lists_contacts_by_list_id_and_contact_id_put` | `ContactsApi#update_contact` |
| `ContactApi#lists_contacts_by_list_id_and_contact_id_delete` | `ContactsApi#delete_contact` |
| `ContactApi#lists_contacts_by_list_id_post` | `ListsApi#create_new_contact` |
| `ContactApi#lists_contacts_by_list_id_get` | `ListsApi#view_list_contacts` |
| `ContactApi#lists_copy_contact_put` | `ListsApi#copy_contact_to_list` |
| `ContactApi#lists_transfer_contact_put` | `ListsApi#transfer_contact_to_list` |
| `ContactApi#lists_remove_opted_out_contacts_by_list_id_and_opt_out_list_id_put` | `ListsApi#remove_opted_out_contacts` |
| `ContactListApi#lists_get` | `ListsApi#view_lists` |
| `ContactListApi#lists_post` | `ListsApi#create_list` |
| `ContactListApi#lists_by_list_id_get` | `ListsApi#view_specific_list` |
| `ContactListApi#lists_by_list_id_put` | `ListsApi#update_list` |
| `ContactListApi#lists_by_list_id_delete` | `ListsApi#delete_list` |
| `ContactListApi#lists_import_by_list_id_post` | `ListsApi#import_contacts` |
| `ContactListApi#lists_remove_duplicates_by_list_id_put` | `ListsApi#remove_duplicate_contacts` |
| `SearchApi#search_contacts_lists_get` | `ListsApi#view_contact_lists` |

> **Correction:** an earlier draft of this guide claimed `SearchApi` had no v2 equivalent. That was wrong — `search_contacts_lists_get` maps directly onto `ListsApi#view_contact_lists`, confirmed present in the generated `lib/clicksend/api/lists_api.rb`.

### Account & billing

| Legacy | v2 |
|---|---|
| `AccountApi#account_get` | `ManagementApi#view_account_details` |
| `AccountApi#account_useage_by_subaccount_get` | `ManagementApi#view_account_usage` |
| `AccountApi#forgot_password_put` | `VerificationApi#forgot_password` |
| `AccountApi#forgot_username_put` | `VerificationApi#forgot_username` |
| `AccountRechargeApi#recharge_credit_card_get` | `TransactionsApi#current_payment_info` |
| `AccountRechargeApi#recharge_credit_card_put` | `TransactionsApi#update_payment_info` |
| `AccountRechargeApi#recharge_packages_get` | `TransactionsApi#view_recharge_packages` |
| `AccountRechargeApi#recharge_purchase_by_package_id_put` | `TransactionsApi#purchase_recharge_package` |
| `AccountRechargeApi#recharge_transactions_get` | `TransactionsApi#view_all_transactions` |
| `AccountRechargeApi#recharge_transactions_by_transaction_id_get` | `TransactionsApi#view_specific_transaction` |
| `ResellerAccountApi#reseller_accounts_get` | `ResellerApi#view_client_accounts` |
| `ResellerAccountApi#reseller_accounts_post` | `ResellerApi#create_reseller_account` |
| `ResellerAccountApi#reseller_accounts_by_client_user_id_get` | `ResellerApi#view_specific_client_account` |
| `ResellerAccountApi#reseller_accounts_by_client_user_id_put` | `ResellerApi#update_client_account` |
| `TransferCreditApi#reseller_transfer_credit_put` | `ResellerApi#reseller_transfer_credit` |
| `SubaccountApi#subaccounts_get` | `SubaccountsApi#view_subaccounts` |
| `SubaccountApi#subaccounts_post` | `SubaccountsApi#create_subaccount` |
| `SubaccountApi#subaccounts_by_subaccount_id_get` | `SubaccountsApi#view_specific_subaccount` |
| `SubaccountApi#subaccounts_by_subaccount_id_put` | `SubaccountsApi#update_subaccount` |
| `SubaccountApi#subaccounts_by_subaccount_id_delete` | `SubaccountsApi#delete_subaccount` |
| `SubaccountApi#subaccounts_regen_api_key_by_subaccount_id_put` | `SubaccountsApi#generate_new_api_key` |
| `ReferralAccountApi#referral_accounts_get` | `ReferralsApi#view_referral_accounts` |

### Numbers, addresses, uploads, international, delivery issues

| Legacy | v2 |
|---|---|
| `NumberApi#numbers_get` | `NumbersApi#view_your_numbers` |
| `NumberApi#numbers_search_by_country_get` | `NumbersApi#view_available_numbers` |
| `NumberApi#numbers_buy_by_dedicated_number_post` | `NumbersApi#purchase_dedicated_number` |
| `PostReturnAddressApi#post_return_addresses_get` | `AddressesApi#view_your_return_addresses` |
| `PostReturnAddressApi#post_return_addresses_post` | `AddressesApi#create_return_address` |
| `PostReturnAddressApi#post_return_addresses_by_return_address_id_get` | `AddressesApi#view_specific_return_address` |
| `PostReturnAddressApi#post_return_addresses_by_return_address_id_put` | `AddressesApi#update_return_address` |
| `PostReturnAddressApi#post_return_addresses_by_return_address_id_delete` | `AddressesApi#delete_return_address` |
| `UploadApi#uploads_post` | `UploadsApi#upload_a_media_file` |
| `CountriesApi#countries_get` | `InternationalMessagingApi#list_countries` |
| `TimezonesApi#timezones_get` | `InternationalMessagingApi#timezones` |
| `GlobalSendingApi#list_countries_get` | `InternationalMessagingApi#get_countries_for_global_sending` |
| `GlobalSendingApi#user_countries_get` | `InternationalMessagingApi#view_countries` |
| `GlobalSendingApi#user_countries_post` | `InternationalMessagingApi#select_countries_for_global_sending` |
| `GlobalSendingApi#user_countries_agree_post` | `InternationalMessagingApi#agree_to_rules_and_regulation` |
| `DeliveryIssuesApi#delivery_issues_get` | `MessageDeliveryApi#get_all_delivery_issues` |
| `DeliveryIssuesApi#delivery_issues_post` | `MessageDeliveryApi#create_delivery_issue` |

### MMS, campaigns, voice, statistics

| Legacy | v2 |
|---|---|
| `MMSApi#mms_send_post` | `MmsApi#send_mms` |
| `MMSApi#mms_history_get` | `MmsApi#view_mms_history` |
| `MMSApi#mms_history_export_get` | `MmsApi#export_mms_history` |
| `MMSApi#mms_price_post` | `MmsApi#calculate_mms_price` |
| `MmsCampaignApi#mms_campaigns_send_post` | `MmsCampaignsApi#send_mms_campaign` |
| `MmsCampaignApi#mms_campaigns_get` | `MmsCampaignsApi#view_all_mms_campaigns` |
| `MmsCampaignApi#mms_campaign_by_mms_campaign_id_get` | `MmsCampaignsApi#view_mms_campaign` |
| `MmsCampaignApi#mms_campaigns_by_mms_campaign_id_put` | `MmsCampaignsApi#update_mms_campaign` |
| `MmsCampaignApi#mms_campaigns_cancel_by_mms_campaign_id_put` | `MmsCampaignsApi#cancel_mms_campaign` |
| `MmsCampaignApi#mms_campaigns_price_post` | `MmsCampaignsApi#calculate_mms_campaign_price` |
| `SmsCampaignApi#sms_campaigns_send_post` | `SmsCampaignsApi#send_sms_campaign` |
| `SmsCampaignApi#sms_campaigns_get` | `SmsCampaignsApi#view_sms_campaigns` |
| `SmsCampaignApi#sms_campaign_by_sms_campaign_id_get` | `SmsCampaignsApi#view_specific_sms_campaign` |
| `SmsCampaignApi#sms_campaigns_by_sms_campaign_id_put` | `SmsCampaignsApi#update_sms_campaign` |
| `SmsCampaignApi#sms_campaigns_cancel_by_sms_campaign_id_put` | `SmsCampaignsApi#cancel_sms_campaign` |
| `SmsCampaignApi#sms_campaigns_price_post` | `SmsCampaignsApi#calculate_sms_campaign_price` |
| `VoiceApi#voice_send_post` | `VoiceMessagingApi#send_voice_message` ⚠️ [§12](#12-the-voice-naming-trap-read-this-before-touching-voice-code) |
| `VoiceApi#voice_history_get` | `VoiceMessagingApi#get_voice_history` |
| `VoiceApi#voice_history_export_get` | `VoiceMessagingApi#export_voice_history` |
| `VoiceApi#voice_price_post` | `VoiceMessagingApi#calculate_voice_price` |
| `VoiceApi#voice_lang_get` | `VoiceMessagingApi#view_voice_languages` |
| `VoiceApi#voice_cancel_all_put` | `VoiceMessagingApi#cancel_all_voice_messages` |
| `VoiceApi#voice_cancel_by_message_id_put` | `VoiceMessagingApi#cancel_voice_message` |
| `VoiceApi#voice_receipts_get` | `VoiceMessagingApi#view_voice_receipts` |
| `VoiceDeliveryReceiptRulesApi#voice_delivery_receipt_automations_get` | `VoiceApi#view_voice_delivery_receipt_rules` ⚠️ [§12](#12-the-voice-naming-trap-read-this-before-touching-voice-code) |
| `VoiceDeliveryReceiptRulesApi#voice_delivery_receipt_automation_get` | `VoiceApi#view_voice_delivery_receipt_rule` |
| `VoiceDeliveryReceiptRulesApi#voice_delivery_receipt_automation_post` | `VoiceApi#create_voice_delivery_receipt_rule` |
| `VoiceDeliveryReceiptRulesApi#voice_delivery_receipt_automation_put` | `VoiceApi#update_voice_delivery_receipt_rule` |
| `VoiceDeliveryReceiptRulesApi#voice_delivery_receipt_automation_delete` | `VoiceApi#delete_voice_delivery_receipt_rule` |
| `StatisticsApi#statistics_sms_get` | `StatisticsApi#view_sms_statistics` |
| `StatisticsApi#statistics_voice_get` | `StatisticsApi#view_voice_statistics` |

### Email-to-SMS: `EmailToSmsApi` → `EmailToSmsApi`

| Legacy | v2 |
|---|---|
| `sms_email_sms_get` | `view_allowed_emails` |
| `sms_email_sms_post` | `add_allowed_email` |
| `sms_email_sms_stripped_string_post` | `create_stripped_string_rule` |
| `sms_email_sms_stripped_string_get` | `view_stripped_string_rule` |
| `sms_email_sms_stripped_strings_get` | `view_stripped_string_rules` |
| `sms_email_sms_stripped_string_put` | `update_stripped_string_rule` |
| `sms_email_sms_stripped_string_delete` | `delete_stripped_string_rule` |

## 11. Side-by-side examples for common operations

### Send an SMS

```ruby
# Legacy
sms_message = ClickSendClient::SmsMessage.new(
  to: '+61411111111',
  body: 'Hello from ClickSend!',
  source: 'ruby'
)
collection = ClickSendClient::SmsMessageCollection.new(messages: [sms_message])

begin
  response = api_instance.sms_send_post(collection)
  puts response                          # raw JSON string
rescue ClickSendClient::ApiError => e
  puts "#{e.code}: #{e.response_body}"
end

# v2
send_sms_request = ClickSend::SendSmsRequest.new(
  messages: [
    { to: '+61411111111', body: 'Hello from ClickSend!', source: 'sdk' }
  ]
)

begin
  response = api_instance.send_sms(send_sms_request: send_sms_request)
  puts response.data.messages.first.status   # typed accessor
rescue ClickSend::ApiError => e
  puts e.message
end
```

### View SMS history

```ruby
# Legacy — all params are optional keys in opts
api_instance.sms_history_get(q: q, date_from: date_from, date_to: date_to, page: page, limit: limit)

# v2 — page/limit/q/date_from/date_to all survive, and order_by is new
api_instance.view_sms_history(
  page: page, limit: limit, q: q, order_by: 'date:desc',
  date_from: date_from, date_to: date_to
)
```

> Always check the current `@option opts` comments on the method — parameter sets changed (this one gained `order_by`).

### Send an MMS / Email / Voice message

Same pattern on every channel — build a `*Request` model (or a plain nested `Hash`), pass it as the matching named key in `opts`:

| Channel | Legacy call | v2 call |
|---|---|---|
| MMS | `mms_api.mms_send_post(mms_message_collection)` | `mms_api.send_mms(send_mms_request: send_mms_request)` |
| Email | `email_api.email_send_post(email)` | `email_api.send_email(send_email_request: send_email_request)` |
| Voice | `voice_api.voice_send_post(voice_collection)` (legacy `VoiceApi`) | `voice_messaging_api.send_voice_message(send_voice_message_request: req)` (⚠️ new `VoiceMessagingApi`, see [§12](#12-the-voice-naming-trap-read-this-before-touching-voice-code)) |

> **Fax, Letters, and Postcards are not part of the v2 SDK** — there is no `send_fax` / `post_letters_send` / `post_postcards_send` equivalent. See [§13](#13-endpointsmethods-removed-in-v2).

### Create a contact in a list

```ruby
# Legacy — contact model first (positional), list_id second (positional)
contact_api.lists_contacts_by_list_id_post(contact, list_id)

# v2 — list_id is now the ONLY positional argument; the payload is a named opts key
lists_api.create_new_contact(
  list_id,
  create_new_contact_request: create_new_contact_request
)
```

### List contacts / lists — pagination parameters were dropped from the method signature

```ruby
# Legacy — page / limit / updated_after were real opts keys
contact_api.lists_contacts_by_list_id_get(list_id, page: page, limit: limit, updated_after: ts)
contact_list_api.lists_get(page: page, limit: limit)
subaccount_api.subaccounts_get(page: page, limit: limit)

# v2 — these opts keys no longer exist on the generated method (only content_type: does)
lists_api.view_list_contacts(list_id)
lists_api.view_lists
subaccounts_api.view_subaccounts
```

**This is a real behavior change, not just a rename.** `ListsApi#view_lists`, `ListsApi#view_list_contacts`, and `SubaccountsApi#view_subaccounts` in the generated v2 SDK only document `content_type:` in `opts` — `page`, `limit`, and `updated_after` are gone from the method signature, even though the underlying REST endpoint's own documentation embedded in the method's doc comment still lists `page`/`limit` as query parameters. Verify against the current API reference how pagination is handled for any workflow that relied on these before you ship — you may need to pass them through `opts[:query_params]` manually as a workaround.

### Create a subaccount

```ruby
# Legacy
subaccount_api.subaccounts_post(subaccount)

# v2
subaccounts_api.create_subaccount(create_subaccount_request: create_subaccount_request)
```

## 12. The Voice naming trap (read this before touching voice code)

This is the single most confusing rename in the whole migration, and a naive search-and-replace of `VoiceApi` will silently point your code at the wrong class:

- Legacy **`VoiceApi`** (send a voice message, view/export history, calculate price, list voice languages, cancel, view receipts) → renamed to new **`VoiceMessagingApi`**.
- Legacy **`VoiceDeliveryReceiptRulesApi`** (create/update/delete/view delivery-receipt rules) → renamed to new **`VoiceApi`**.

The new `VoiceApi` has **nothing to do with sending voice calls** — it is purely the old delivery-receipt-rules class under a new name. To migrate voice-sending code, use `VoiceMessagingApi`:

```ruby
# Wrong — this runs, but VoiceApi in v2 only has delivery-receipt-rule methods
voice_api = ClickSend::VoiceApi.new
voice_api.send_voice_message(...)          # NoMethodError

# Correct
voice_messaging_api = ClickSend::VoiceMessagingApi.new
voice_messaging_api.send_voice_message(send_voice_message_request: req)
```

## 13. Endpoints/methods removed in v2

### Entire products dropped

The **Fax**, **Letters**, and **Postcards** products have **no presence at all** in the v2 SDK — no API class, no models. If your integration sends faxes, letters, or postcards, there is currently no v2 SDK path for it; call the REST API directly or stay on the legacy SDK for those channels.

| Legacy class(es) | Covered (legacy) | v2 |
|---|---|---|
| `FaxApi`, `FaxDeliveryReceiptRulesApi`, `InboundFaxRulesApi` | send fax, fax history/export, fax price, fax receipts, fax delivery-receipt rules, inbound fax rules | _none_ |
| `PostLetterApi` | send letter, letter history/export, letter price | _none_ |
| `PostPostcardApi` | send postcard, postcard history/export, postcard price | _none_ |
| `DetectAddressApi` | address detection/parsing (`detect_address_post`) | _none_ |

### Individual methods dropped (class otherwise survived)

The following legacy operations have **no equivalent anywhere in the v2 SDK**. If your integration depends on any of these, check the current ClickSend API reference before upgrading — the underlying endpoint may have been retired, moved, or simply not covered by the new spec at build time:

- `AccountApi#account_post` — update account details
- `AccountApi#account_verify_send_put` — send account verification email
- `AccountApi#account_verify_verify_by_activation_token_put` — verify account by activation token
- `AccountApi#forgot_password_verify_put` — verify a forgotten-password token
- `MMSApi#mms_receipts_get` — view MMS delivery receipts
- `MMSApi#mms_receipts_read_put` — mark MMS receipts as read
- `VoiceApi#voice_receipts_post` (legacy class) — create a test voice receipt
- `VoiceApi#voice_receipts_read_put` (legacy class) — mark voice receipts as read

Additionally, **pagination parameters (`page`, `limit`, `updated_after`) were dropped** from several generated method signatures even where the class survived — notably `ListsApi#view_lists`, `ListsApi#view_list_contacts`, and `SubaccountsApi#view_subaccounts` (see [§11](#11-side-by-side-examples-for-common-operations)).

## 14. Brand-new resources and methods in v2

No legacy counterpart at all — nothing to migrate, but worth knowing they exist:

- **`AlphaTagsApi`** — `list_alpha_tags`, `get_alpha_tag`, `request_alpha_tag`, `delete_alpha_tag`
- **`DefaultSendersApi`** — `get_default_senders_list`, `get_default_sender_details`, `create_default_sender`, `update_default_sender`, `delete_default_sender`, `list_compliant_sender_types`
- **`OwnNumbersApi`** (Bring Your Own Number) — `list_own_numbers`, `get_own_number_detail`, `update_own_number`, `delete_own_number`, `request_own_number_verification_otp`, `verify_own_number_otp`
- **`UrlShorteningApi`** — `short_url_get_statistics`, `short_url_get_tracking`
- **`NumbersApi#register_numbers`** — number registration (alongside the renamed `NumberApi` methods)
- **`SmsApi#view_a_specific_inbound_sms_message`** and **`SmsApi#view_a_specific_sms_template`** — fetch a single inbound message / template by ID (legacy only exposed the list endpoints)

## 15. Step-by-step migration checklist

1. **Swap the dependency**: remove `gem 'clicksend_client'` from your Gemfile, add `gem 'clicksend', git: 'https://github.com/ClickSend/clicksend-ruby-v2.git'`, run `bundle install` (confirm the current distribution channel for your account first — see [§2](#2-installation--imports)).
2. **Rename the require**: `require 'clicksend_client'` → `require 'clicksend'` everywhere.
3. **Rename every module reference**: `ClickSendClient::` → `ClickSend::`, including `ClickSendClient.configure` → `ClickSend.configure` and every `*Api.new` (`SMSApi` → `SmsApi`, `MMSApi` → `MmsApi`, …). **Pay special attention to `VoiceApi` → `VoiceMessagingApi`** ([§12](#12-the-voice-naming-trap-read-this-before-touching-voice-code)).
4. **Re-check any custom `config.base_path` / `config.host` overrides** against v2's defaults ([§4](#4-base-path--url-changes)).
5. **Rebuild every request payload** with the matching `*Request` model (or a plain nested `Hash`), and pass it as a **named key inside the `opts` hash** rather than as a positional argument ([§6](#6-request-payloads-request-models-replace-reusable-domain-models)). Path/ID parameters (e.g. `list_id`, `template_id`) stay positional.
6. **Rename every method call** using the [§10](#10-class-by-class-mapping-all-37-legacy-classes)/[§11](#11-side-by-side-examples-for-common-operations) tables or the `docs/` folder in the v2 repo.
7. **Re-check parameters** for every call — several methods dropped pagination params (`page`/`limit`/`updated_after`) entirely, and some gained new ones (`order_by`) ([§11](#11-side-by-side-examples-for-common-operations), [§13](#13-endpointsmethods-removed-in-v2)).
8. **Update response handling** — the return value is now a typed model object, not a raw JSON string. Delete manual `JSON.parse` / hash-key digging (`result['data']`) and replace with attribute access (`result.data`); use `to_hash`/`to_body` when you need a plain `Hash` ([§7](#7-response-payloads-are-now-properly-typed)).
9. **Update error handling** — fix the `ApiError` namespace (`ClickSendClient::ApiError` → `ClickSend::ApiError`), and simplify any `rescue` block that manually formatted `code`/`response_body` to just use `e.message` ([§8](#8-error-handling-changes)).
10. **Check for removed endpoints and dropped products** ([§13](#13-endpointsmethods-removed-in-v2)) — the entire Fax, Letters, and Postcards products are gone — and confirm a replacement exists in the current API before shipping.
11. **Test each migrated call against ClickSend sandbox/test credentials** before deploying. Ruby won't catch renamed methods or reshuffled arguments until runtime, so smoke-test every endpoint your integration uses.
