# ClickSend::ResellerAccount

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **user_id** | **Integer** | The user&#39;s ID | [optional] |
| **username** | **String** | The username | [optional] |
| **user_email** | **String** | The user&#39;s email | [optional] |
| **active** | **Integer** | Indicates if the user is active | [optional] |
| **banned** | **Integer** | Indicates if the user is banned | [optional] |
| **balance** | **String** | The user&#39;s balance | [optional] |
| **user_phone** | **String** | The user&#39;s phone number | [optional] |
| **reply_to** | **String** | The reply-to email address | [optional] |
| **delivery_to** | **String** | The delivery-to email address | [optional] |
| **user_first_name** | **String** | The user&#39;s first name | [optional] |
| **user_last_name** | **String** | The user&#39;s last name | [optional] |
| **account** | **Integer** | The user&#39;s account number | [optional] |
| **account_name** | **String** | The name of the user&#39;s account | [optional] |
| **account_billing_email** | **String** | The account billing email | [optional] |
| **account_billing_mobile** | **String** | The account billing mobile number | [optional] |
| **country** | **String** | The user&#39;s country | [optional] |
| **default_country_sms** | **String** | The default country for SMS | [optional] |
| **auto_recharge** | **Integer** | Indicates if auto-recharge is enabled | [optional] |
| **auto_recharge_amount** | **String** | The auto-recharge amount | [optional] |
| **low_credit_amount** | **String** | The low credit amount | [optional] |
| **setting_unicode_sms** | **Integer** | Setting for Unicode SMS | [optional] |
| **setting_email_sms_subject** | **Integer** | Setting for email SMS subject | [optional] |
| **setting_fix_sender_id** | **Integer** | Setting for fixed sender ID | [optional] |
| **setting_sms_message_char_limit** | **Integer** | Setting for SMS message character limit | [optional] |
| **old_dashboard** | **Integer** | Indicates if the user is using the old dashboard | [optional] |
| **balance_commission** | **String** | The balance commission | [optional] |
| **timezone** | **String** | The user&#39;s timezone | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ResellerAccount.new(
  user_id: 117,
  username: johndoe2,
  user_email: johndoe2@awesome.com,
  active: 0,
  banned: 0,
  balance: 0.000000,
  user_phone: 15184811002,
  reply_to: originalemail,
  delivery_to: null,
  user_first_name: John,
  user_last_name: Doe,
  account: 0,
  account_name: The Awesome Company,
  account_billing_email: johndoe2@awesome.com,
  account_billing_mobile: 15184811002,
  country: US,
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
  timezone: Australia/Melbourne
)
```

