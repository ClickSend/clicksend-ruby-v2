# ClickSend::CreateSubaccount

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

instance = ClickSend::CreateSubaccount.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: New account has been created.,
  data: null
)
```

