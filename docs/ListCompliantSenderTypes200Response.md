# ClickSend::ListCompliantSenderTypes200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | HTTP status code of the response |  |
| **response_code** | **String** | Code indicating the result of the response |  |
| **response_msg** | **String** | Message providing additional information |  |
| **data** | [**ListCompliantSenderTypes200ResponseData**](ListCompliantSenderTypes200ResponseData.md) |  |  |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ListCompliantSenderTypes200Response.new(
  http_code: null,
  response_code: null,
  response_msg: null,
  data: null
)
```

