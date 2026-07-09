# ClickSend::CalculateEmailCampaignPriceData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_count** | **Float** | The total count of the email campaigns. | [optional] |
| **total_price** | **String** | The total price of the email campaigns. | [optional] |
| **queued_count** | **Float** | The count of the queued email campaigns. | [optional] |
| **data** | [**CalculateEmailCampaignPriceDataData**](CalculateEmailCampaignPriceDataData.md) |  | [optional] |
| **_currency** | [**Currency**](Currency.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CalculateEmailCampaignPriceData.new(
  total_count: 1,
  total_price: 0.0066,
  queued_count: 2,
  data: null,
  _currency: null
)
```

