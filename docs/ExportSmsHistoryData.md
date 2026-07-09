# ClickSend::ExportSmsHistoryData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **url** | **String** | The download link to the generated SMS history file. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ExportSmsHistoryData.new(
  url: https://rest.clicksend.com/files/22D55AF9-6CF0-476D-A8B3-82A998FD2738?filename&#x3D;export.csv
)
```

