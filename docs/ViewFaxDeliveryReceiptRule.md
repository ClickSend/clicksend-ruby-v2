# ClickSend::ViewFaxDeliveryReceiptRule

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP status code of the response. | [optional] |
| **response_code** | **String** | The response code indicating the status of the operation. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | [**FaxDeliveryReceiptRule**](FaxDeliveryReceiptRule.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewFaxDeliveryReceiptRule.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: Your rule incoming fax receipt.,
  data: null
)
```

