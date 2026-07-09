# ClickSend::CreateSubaccountRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **api_username** | **String** |  | [optional] |
| **password** | **String** |  | [optional] |
| **email** | **String** |  | [optional] |
| **phone_number** | **String** |  | [optional] |
| **first_name** | **String** |  | [optional] |
| **last_name** | **String** |  | [optional] |
| **user_id** | **Integer** |  | [optional] |
| **sms_deidentify_message** | **Integer** |  | [optional] |
| **access_smpp** | **Integer** |  | [optional] |
| **access_users** | **Integer** |  | [optional] |
| **access_billing** | **Integer** |  | [optional] |
| **access_reporting** | **Integer** |  | [optional] |
| **access_contacts** | **Integer** |  | [optional] |
| **access_settings** | **Integer** |  | [optional] |
| **notes** | **String** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CreateSubaccountRequest.new(
  api_username: null,
  password: null,
  email: null,
  phone_number: null,
  first_name: null,
  last_name: null,
  user_id: null,
  sms_deidentify_message: null,
  access_smpp: null,
  access_users: null,
  access_billing: null,
  access_reporting: null,
  access_contacts: null,
  access_settings: null,
  notes: null
)
```

