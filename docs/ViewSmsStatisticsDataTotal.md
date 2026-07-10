# ClickSend::ViewSmsStatisticsDataTotal

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **outbound** | [**ViewVoiceStatisticsDataTotalOutbound**](ViewVoiceStatisticsDataTotalOutbound.md) |  | [optional] |
| **inbound** | [**CancelAllSmsData**](CancelAllSmsData.md) |  | [optional] |
| **bounced** | [**CancelAllSmsData**](CancelAllSmsData.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewSmsStatisticsDataTotal.new(
  outbound: null,
  inbound: null,
  bounced: null
)
```

