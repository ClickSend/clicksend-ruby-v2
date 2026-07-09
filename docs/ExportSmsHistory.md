# ClickSend::ExportSmsHistory

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP code of the response. Visit [this page](/#status-codes) for more information. | [optional] |
| **response_code** | **String** | The response code of the operation. Visit [this page](/#status-codes) for more information. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | [**ExportSmsHistoryData**](ExportSmsHistoryData.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ExportSmsHistory.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: Download your file here.,
  data: null
)
```

