# ClickSend::CalculateVoicePrice

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP status code of the response. | [optional] |
| **response_code** | **String** | The response code indicating the status of the operation. | [optional] |
| **response_msg** | **String** | Here are your data. | [optional] |
| **data** | [**SendVoiceMessageData**](SendVoiceMessageData.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CalculateVoicePrice.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: null,
  data: null
)
```

