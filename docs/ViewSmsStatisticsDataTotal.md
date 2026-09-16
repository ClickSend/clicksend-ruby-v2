# ClickSend::ViewSmsStatisticsDataTotal

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **outbound** | [**ViewVoiceStatisticsDataTotalOutbound**](ViewVoiceStatisticsDataTotalOutbound.md) |  | [optional] |
| **inbound** | [**ViewVoiceStatisticsDataTotalOutbound**](ViewVoiceStatisticsDataTotalOutbound.md) |  | [optional] |
| **bounced** | [**ViewVoiceStatisticsDataTotalOutbound**](ViewVoiceStatisticsDataTotalOutbound.md) |  | [optional] |

## Example

```ruby
require 'clicksend_client'

instance = ClickSend::ViewSmsStatisticsDataTotal.new(
  outbound: null,
  inbound: null,
  bounced: null
)
```

