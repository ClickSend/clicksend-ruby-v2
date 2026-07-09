# ClickSend::CalculateSmsCampaignPriceData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_count** | **Integer** | The total number of records. | [optional] |
| **total_price** | **Float** | The total price of the SMS campaign. | [optional] |
| **data** | [**CalculateSmsCampaignPriceDataData**](CalculateSmsCampaignPriceDataData.md) |  | [optional] |
| **_currency** | [**Currency**](Currency.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CalculateSmsCampaignPriceData.new(
  total_count: 1,
  total_price: 0.035,
  data: null,
  _currency: null
)
```

