# ClickSend::Model400Error

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

instance = ClickSend::Model400Error.new(
  http_code: 400,
  response_code: BAD_REQUEST,
  response_msg: Invalid input.,
  data: {&quot;name&quot;:&quot;Name field is required.&quot;,&quot;email&quot;:&quot;Email field is required.&quot;}
)
```

