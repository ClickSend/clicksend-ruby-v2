# ClickSend::RegisterNumbers

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | HTTP status code of the response. |  |
| **response_code** | **String** | Code indicating the result of the response. |  |
| **response_msg** | **String** | Message providing additional information. |  |
| **data** | **Object** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::RegisterNumbers.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: 10DLC number registration notification sent successfully.,
  data: null
)
```

