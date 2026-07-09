# ClickSend::CalculateMmsCampaignPriceData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_count** | **String** | The total number of records. | [optional] |
| **total_price** | **String** | The total price of the MMS campaign. | [optional] |
| **data** | [**CalculateMmsCampaignPriceDataData**](CalculateMmsCampaignPriceDataData.md) |  | [optional] |
| **_currency** | [**Currency**](Currency.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CalculateMmsCampaignPriceData.new(
  total_count: 1,
  total_price: 0.429,
  data: null,
  _currency: null
)
```

