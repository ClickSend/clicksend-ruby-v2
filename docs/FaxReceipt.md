# ClickSend::FaxReceipt

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **timestamp_send** | **String** | The timestamp when the message was sent. | [optional] |
| **timestamp** | **String** | The timestamp associated with the message. | [optional] |
| **message_id** | **String** | The ID of the message. | [optional] |
| **status_code** | **String** | The status code of the message. | [optional] |
| **status_text** | **String** | The status text of the message. | [optional] |
| **error_code** | **String** | The error code associated with the message. | [optional] |
| **error_text** | **String** | The error text associated with the message. | [optional] |
| **custom_string** | **String** | A custom string associated with the message. | [optional] |
| **subaccount_id** | **Integer** | The ID of the subaccount. | [optional] |
| **message_type** | **String** | The type of message. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::FaxReceipt.new(
  timestamp_send: 1450854013,
  timestamp: 1451200622,
  message_id: 88AB118E-EB1B-478C-98CE-6C73ABA23F67,
  status_code: Completed,
  status_text: ,
  error_code: ,
  error_text: ,
  custom_string: ,
  subaccount_id: 1,
  message_type: fax
)
```

