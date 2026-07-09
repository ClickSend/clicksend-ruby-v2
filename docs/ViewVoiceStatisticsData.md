# ClickSend::ViewVoiceStatisticsData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total** | [**ViewVoiceStatisticsDataTotal**](ViewVoiceStatisticsDataTotal.md) |  | [optional] |
| **stats** | [**Array&lt;ViewVoiceStatisticsDataStatsInner&gt;**](ViewVoiceStatisticsDataStatsInner.md) |  | [optional] |
| **_currency** | [**Currency**](Currency.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewVoiceStatisticsData.new(
  total: null,
  stats: null,
  _currency: null
)
```

