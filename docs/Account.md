# ClickSend::Account

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **user_id** | **Integer** | The unique identifier for the user. | [optional] |
| **username** | **String** | The username of the user. | [optional] |
| **user_email** | **String** | The email address of the user. | [optional] |
| **active** | **Integer** | Flag indicating if the user account is active. | [optional] |
| **banned** | **Integer** | Flag indicating if the user account is banned. | [optional] |
| **date_sign_up** | **Integer** | The Unix timestamp of when the account was created. | [optional] |
| **balance** | **String** | The balance of the user&#39;s account. | [optional] |
| **user_phone** | **String** | The phone number of the user. | [optional] |
| **reply_to** | **String** | The email address to reply to. | [optional] |
| **delivery_to** | **String** | The delivery email address. | [optional] |
| **user_first_name** | **String** | The first name of the user. | [optional] |
| **user_last_name** | **String** | The last name of the user. | [optional] |
| **account** | **Integer** | The account number. | [optional] |
| **account_name** | **String** | The name of the account. | [optional] |
| **account_billing_email** | **String** | The billing email address of the account. | [optional] |
| **account_billing_mobile** | **String** | The billing mobile number of the account. | [optional] |
| **priority** | **Integer** | The account&#39;s priority tier. | [optional] |
| **country** | **String** | The country of the user. | [optional] |
| **country_ip** | **String** | The country the user is currently connecting from, based on IP address. | [optional] |
| **default_country_sms** | **String** | The default country for SMS. | [optional] |
| **auto_recharge** | **Integer** | Flag indicating if auto-recharge is enabled. | [optional] |
| **auto_recharge_amount** | **String** | The auto-recharge amount. | [optional] |
| **low_credit_amount** | **String** | The low credit amount. | [optional] |
| **setting_unicode_sms** | **Integer** | Flag indicating if unicode SMS is enabled. | [optional] |
| **setting_email_sms_subject** | **Integer** | Flag indicating if email SMS subject is enabled. | [optional] |
| **setting_fix_sender_id** | **Integer** | Flag indicating if fixing sender ID is enabled. | [optional] |
| **setting_sms_message_char_limit** | **Integer** | The SMS message character limit. | [optional] |
| **old_dashboard** | **Integer** | Flag indicating if old dashboard is enabled. | [optional] |
| **balance_commission** | **String** | The balance commission. | [optional] |
| **timezone** | **String** | The timezone of the user. | [optional] |
| **price_rate** | **Integer** | The pricing tier used to determine the cost per message. | [optional] |
| **private_uploads** | **Integer** | Flag indicating if uploaded media is kept private. | [optional] |
| **fax_quality** | **Integer** | The quality setting used for outgoing faxes. | [optional] |
| **setting_sms_hide_your_number** | **Integer** | Flag indicating if your number is hidden on outgoing SMS. | [optional] |
| **setting_sms_hide_business_name** | **Integer** | Flag indicating if the business name is hidden on outgoing SMS. | [optional] |
| **pricing_variant** | **Integer** | The pricing variant applied to the account. | [optional] |
| **on_trial** | **Integer** | Flag indicating if the account is currently on a trial. | [optional] |
| **trial_expiry** | **String** | The date the trial expires, if the account is on a trial. | [optional] |
| **_currency** | [**Currency**](Currency.md) |  | [optional] |
| **_subaccount** | [**Subaccount**](Subaccount.md) |  | [optional] |
| **_referrer_chosen** | [**AccountReferrerChosen**](AccountReferrerChosen.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::Account.new(
  user_id: 116,
  username: johndoe1,
  user_email: johndoe1@awesome.com,
  active: 0,
  banned: 0,
  date_sign_up: 1436871253,
  balance: 4.998000,
  user_phone: +15184811001,
  reply_to: originalemail,
  delivery_to: null,
  user_first_name: John,
  user_last_name: Doe,
  account: 0,
  account_name: The Awesome Company,
  account_billing_email: johndoe1@awesome.com,
  account_billing_mobile: +15184811001,
  priority: 2,
  country: US,
  country_ip: US,
  default_country_sms: US,
  auto_recharge: 0,
  auto_recharge_amount: 20.00,
  low_credit_amount: 0.00,
  setting_unicode_sms: 0,
  setting_email_sms_subject: 0,
  setting_fix_sender_id: 0,
  setting_sms_message_char_limit: 6,
  old_dashboard: 0,
  balance_commission: 0.299954,
  timezone: Australia/Melbourne,
  price_rate: 0,
  private_uploads: 0,
  fax_quality: 0,
  setting_sms_hide_your_number: 0,
  setting_sms_hide_business_name: 0,
  pricing_variant: 0,
  on_trial: 0,
  trial_expiry: null,
  _currency: null,
  _subaccount: null,
  _referrer_chosen: null
)
```

