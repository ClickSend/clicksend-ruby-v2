# ClickSend::CalculateSmsCampaignPriceDataData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **from** | **String** | The sender. | [optional] |
| **body** | **String** | The message body. | [optional] |
| **schedule** | **Integer** | The schedule timestamp. | [optional] |

## Example

```ruby
require 'clicksend_client'

instance = ClickSend::CalculateSmsCampaignPriceDataData.new(
  from: +61353787448,
  body: John, this is your new campaign message.,
  schedule: 1444381346
)
```

