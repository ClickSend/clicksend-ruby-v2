# ClickSend::ViewVoiceStatisticsDataTotalOutbound

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **count** | **Integer** | The total count of outbound calls. | [optional] |
| **price** | **Float** | The total price of outbound calls. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewVoiceStatisticsDataTotalOutbound.new(
  count: 1,
  price: 0
)
```

