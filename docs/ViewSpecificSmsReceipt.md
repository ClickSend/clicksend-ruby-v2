# ClickSend::ViewSpecificSmsReceipt

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP code of the response. Visit [this page](/#status-codes) for more information.  This parameter doesn’t reflect the status of each message. Check the _status_ parameter of the message object to view the status of the individual message. | [optional] |
| **response_code** | **String** | The response code of the operation. Visit [this page](/#status-codes) for more information. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | [**SmsReceipt**](SmsReceipt.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewSpecificSmsReceipt.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: Your receipt.,
  data: null
)
```

