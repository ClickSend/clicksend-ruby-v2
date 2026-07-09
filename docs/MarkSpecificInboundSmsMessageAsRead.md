# ClickSend::MarkSpecificInboundSmsMessageAsRead

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP code of the response. Visit [this page](/#status-codes) for more information. | [optional] |
| **response_code** | **String** | The response code of the operation. Visit [this page](/#status-codes) for more information. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | **Integer** | The number of SMS marked as read.  If you have multiple inbound rules set to POLL, you will receive the inbound message multiple times. Reading it will mark all those messages as read. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::MarkSpecificInboundSmsMessageAsRead.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: Receipt have been marked as read.,
  data: 1
)
```

