# ClickSend::ViewSmsStatisticsData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total** | [**ViewSmsStatisticsDataTotal**](ViewSmsStatisticsDataTotal.md) |  | [optional] |
| **stats** | [**Array&lt;ViewSmsStatisticsDataStatsInner&gt;**](ViewSmsStatisticsDataStatsInner.md) |  | [optional] |
| **_currency** | [**Currency**](Currency.md) |  | [optional] |

## Example

```ruby
require 'clicksend_client'

instance = ClickSend::ViewSmsStatisticsData.new(
  total: null,
  stats: null,
  _currency: null
)
```

