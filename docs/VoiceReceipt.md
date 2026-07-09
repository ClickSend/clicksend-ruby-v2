# ClickSend::VoiceReceipt

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **timestamp_send** | **String** | Timestamp of the original send request in UNIX format. e.g 1439173980 | [optional] |
| **timestamp** | **String** | Timestamp of delivery report in UNIX format. e.g 1439173981 | [optional] |
| **message_id** | **String** | Message ID, returned when originally sending the message. | [optional] |
| **status_code** | **String** | Status code. Refer to &#39;Voice Delivery Status Codes&#39; in docs. | [optional] |
| **status_text** | **String** | Status text. | [optional] |
| **error_code** | **String** | Error code. | [optional] |
| **error_text** | **String** | Error text. | [optional] |
| **custom_string** | **String** | A custom string used when sending the original message. | [optional] |
| **message_type** | **String** | voice (constant). | [optional] |
| **digits** | **String** | Numbers the recipient pressed on their keypad during the call. A blank string will be used if they didn&#39;t provide any input. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::VoiceReceipt.new(
  timestamp_send: 1442381791,
  timestamp: 1442381791,
  message_id: 31BC271B-1E0C-45F6-9E7E-97186C46BB82,
  status_code: 201,
  status_text: Success: Message received on handset.,
  error_code: null,
  error_text: null,
  custom_string: null,
  message_type: voice,
  digits: null
)
```

