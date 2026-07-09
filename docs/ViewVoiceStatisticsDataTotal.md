# ClickSend::ViewVoiceStatisticsDataTotal

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **outbound** | [**ViewVoiceStatisticsDataTotalOutbound**](ViewVoiceStatisticsDataTotalOutbound.md) |  | [optional] |
| **bounced** | [**CancelAllSmsData**](CancelAllSmsData.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewVoiceStatisticsDataTotal.new(
  outbound: null,
  bounced: null
)
```

