# ClickSend Ruby SDK

[![Ruby](https://img.shields.io/badge/ruby-2.7%2B-blue.svg)](https://www.ruby-lang.org/)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![API: v3](https://img.shields.io/badge/ClickSend%20API-v3-brightgreen.svg)](https://developers.clicksend.com/docs/rest/v3/)

Official Ruby gem for the [ClickSend API](https://developers.clicksend.com/) — send SMS, MMS, voice and email messages, run SMS and MMS campaigns, manage numbers, contacts and subaccounts, and pull delivery receipts and reporting through a single authenticated HTTPS client.

This library is generated from ClickSend's official OpenAPI v3 specification and is maintained by ClickSend. It covers every endpoint of the [ClickSend REST API](https://developers.clicksend.com/docs/rest/v3/).

- 📚 **API reference:** https://developers.clicksend.com/docs/rest/v3/
- 🔑 **Dashboard & API credentials:** https://dashboard.clicksend.com
- 🗂 **Source & issues:** https://github.com/ClickSend/clicksend-ruby-v2
- 💬 **Support:** https://help.clicksend.com

## Features

- **Messaging** — SMS, MMS, voice / text-to-speech, transactional email, email-to-SMS
- **Campaigns** — SMS and MMS campaigns
- **Numbers & sender IDs** — dedicated numbers, own numbers, alpha tags, default senders
- **Contacts** — contact lists, contacts and the address book
- **Account & billing** — account details, transactions, subaccounts, referrals, reseller accounts
- **Delivery & reporting** — delivery receipts, inbound messages, statistics
- **Extras** — URL shortening, file uploads, number verification, international messaging
- **Typed models** for every request and response
- **HTTP Basic auth** with your ClickSend username and API key
- **Identifiable traffic** — requests are sent with a `ClickSend-SDK/<version>/ruby` `User-Agent` by default
- MIT licensed

## Requirements

- Ruby 2.7 or newer

## Installation

Add this to your Gemfile:

```ruby
gem 'clicksend', :git => 'https://github.com/ClickSend/clicksend-ruby-v2.git'
```

Then run:

```sh
bundle install
```

## Authentication

Every API class authenticates with HTTP Basic auth using your ClickSend **username** and **API key**, both available from the [ClickSend Dashboard](https://dashboard.clicksend.com/#/account/subaccount). Supply them through environment variables rather than hard-coding them:

```sh
export CLICKSEND_USERNAME="your-username"
export CLICKSEND_API_KEY="your-api-key"
```

## Quickstart

```ruby
require 'clicksend'

ClickSend.configure do |config|
  config.username = ENV['CLICKSEND_USERNAME']
  config.password = ENV['CLICKSEND_API_KEY']
end

api_instance = ClickSend::SmsApi.new
send_sms_request = ClickSend::SendSmsRequest.new(
  messages: [
    { source: 'sdk', body: 'Hello from ClickSend!', to: '+61411111111' }
  ]
)

begin
  result = api_instance.send_sms(send_sms_request: send_sms_request)
  p result
rescue ClickSend::ApiError => e
  puts "Exception when calling SmsApi->send_sms: #{e}"
end
```

## More Examples

### View account details

```ruby
api_instance = ClickSend::ManagementApi.new

begin
  result = api_instance.view_account_details
  p result
rescue ClickSend::ApiError => e
  puts "Exception when calling ManagementApi->view_account_details: #{e}"
end
```

### Send an MMS

```ruby
api_instance = ClickSend::MmsApi.new
send_mms_request = ClickSend::SendMmsRequest.new(
  media_file: 'https://clicksend.com/logo.png',
  messages: [
    { source: 'sdk', to: '+61411111111', from: 'sdk', subject: 'Hello', body: 'Hello from ClickSend!' }
  ]
)

begin
  result = api_instance.send_mms(send_mms_request: send_mms_request)
  p result
rescue ClickSend::ApiError => e
  puts "Exception when calling MmsApi->send_mms: #{e}"
end
```

## Configuration

```ruby
ClickSend.configure do |config|
  config.username = ENV['CLICKSEND_USERNAME']
  config.password = ENV['CLICKSEND_API_KEY']
  # Override the API base URL (default: https://rest.clicksend.com).
  config.host = 'rest.clicksend.com'
  config.scheme = 'https'
  config.timeout = 30
end
```

## Error Handling

Non-2xx responses raise `ClickSend::ApiError`:

```ruby
begin
  result = api_instance.send_sms(send_sms_request: send_sms_request)
rescue ClickSend::ApiError => e
  e.code           # HTTP status code
  e.response_body  # raw error payload from the API
  e.response_headers
end
```

## Documentation

- Full REST API reference: https://developers.clicksend.com/docs/rest/v3/
- Per-endpoint SDK docs: the [`docs/`](docs) directory in this repository
- Source code: https://github.com/ClickSend/clicksend-ruby-v2

## Versioning

This gem follows [semantic versioning](https://semver.org/). Breaking changes are released as major versions.

## Support

- Help Centre: https://help.clicksend.com
- Contact support: https://clicksend.com/contact
- SDK bugs and feature requests: https://github.com/ClickSend/clicksend-ruby-v2/issues

## License

Released under the [MIT License](https://opensource.org/licenses/MIT).

---

**Keywords:** clicksend, sms, sms api, send sms, bulk sms, text message, texting, mms, mms api, voice, voice call, text to speech, tts, ivr, email to sms, sms campaign, mms campaign, url shortening, number verification, messaging, notifications, otp, 2fa, two factor authentication, transactional sms, marketing sms, appointment reminders, alerts, ruby, rails, gem, rest api, clicksend sdk
