# ClickSend::OwnNumber

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | The unique identifier for the record. | [optional] |
| **account_id** | **String** | The unique identifier for the account. | [optional] |
| **workspace_id** | **String** | The unique identifier for the workspace. | [optional] |
| **user_id** | **String** | The unique identifier for the user. | [optional] |
| **phone_number** | **String** | The user&#39;s phone number. | [optional] |
| **country** | **String** | The country code of the phone number. | [optional] |
| **label** | **String** | A label for the phone number. | [optional] |
| **status** | **String** | The status of the phone number. | [optional] |
| **verified_timestamp** | **Time** | The timestamp when the phone number was verified. | [optional] |
| **is_nearing_expiration** | **Boolean** | Indicates whether the phone number verification is nearing its expiration date: - **true:** The verification was completed more than 11 months ago and will expire soon. You should re-verify your phone number to maintain uninterrupted service. - **false:** The verification is still valid and not approaching expiration. | [optional] |
| **created_timestamp** | **Time** | The timestamp when the record was created. | [optional] |
| **updated_timestamp** | **Time** | The timestamp when the record was last updated. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::OwnNumber.new(
  id: 8fa5ebc2-777b-45db-a448-ec76a40d4384,
  account_id: 85edb794-ee6d-4a38-9f63-c5fa8acf0d79,
  workspace_id: 85edb794-ee6d-4a38-9f63-c5fa8acf0d79,
  user_id: 85edb794-ee6d-4a38-9f63-c5fa8acf0d79,
  phone_number: +61412345678,
  country: AU,
  label: My phone number,
  status: APPROVED,
  verified_timestamp: 2023-08-31T12:00Z,
  is_nearing_expiration: true,
  created_timestamp: 2023-08-25T08:00Z,
  updated_timestamp: 2023-08-25T08:30Z
)
```

