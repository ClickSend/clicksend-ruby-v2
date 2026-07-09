# ClickSend::UpdateSubaccount

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP status code of the response. | [optional] |
| **response_code** | **String** | The response code indicating the status of the operation. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | [**Subaccount**](Subaccount.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::UpdateSubaccount.new(
  http_code: null,
  response_code: null,
  response_msg: null,
  data: null
)
```

