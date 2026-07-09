# ClickSend::ViewSmsStatisticsDataStatInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **date** | **Float** | The date. | [optional] |
| **outbound** | [**ViewVoiceStatisticsDataStatsInnerOutbound**](ViewVoiceStatisticsDataStatsInnerOutbound.md) |  | [optional] |
| **inbound** | [**CancelAllSmsData**](CancelAllSmsData.md) |  | [optional] |
| **bounced** | [**CancelAllSmsData**](CancelAllSmsData.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewSmsStatisticsDataStatInner.new(
  date: 1436918400,
  outbound: null,
  inbound: null,
  bounced: null
)
```

