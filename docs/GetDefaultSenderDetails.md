# ClickSend::GetDefaultSenderDetails

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | HTTP status code of the response. |  |
| **response_code** | **String** | Code indicating the result of the response. |  |
| **response_msg** | **String** | Message providing additional information. |  |
| **data** | [**DefaultSender**](DefaultSender.md) |  |  |

## Example

```ruby
require 'clicksend'

instance = ClickSend::GetDefaultSenderDetails.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: Operation completed successfully,
  data: null
)
```

