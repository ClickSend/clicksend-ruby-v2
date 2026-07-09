# ClickSend::UpdatePaymentInfo

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP status code of the response. | [optional] |
| **response_code** | **String** | The response code indicating the status of the operation. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | [**UpdatePaymentInfoData**](UpdatePaymentInfoData.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::UpdatePaymentInfo.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: Your payment info has been updated.,
  data: null
)
```

