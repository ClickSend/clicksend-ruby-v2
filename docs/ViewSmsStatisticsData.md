# ClickSend::ViewSmsStatisticsData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total** | [**ViewSmsStatisticsDataTotal**](ViewSmsStatisticsDataTotal.md) |  | [optional] |
| **stat** | [**Array&lt;ViewSmsStatisticsDataStatInner&gt;**](ViewSmsStatisticsDataStatInner.md) |  | [optional] |
| **_currency** | [**Currency**](Currency.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewSmsStatisticsData.new(
  total: null,
  stat: null,
  _currency: null
)
```

