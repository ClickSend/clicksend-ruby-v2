# ClickSend::GetTrackingDataInnerContact

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **contact_id** | **String** | Contact ID of the recipient. Null if the recipient is not a contact. | [optional] |
| **first_name** | **String** | First name of the recipient. Null if the recipient has no data for first name. | [optional] |
| **last_name** | **String** | Last name of the recipient. Null if the recipient has no data last name. | [optional] |
| **phone_number** | **String** | Phone number of the recipient | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::GetTrackingDataInnerContact.new(
  contact_id: 224466,
  first_name: John,
  last_name: Doe,
  phone_number: +1234567890
)
```

