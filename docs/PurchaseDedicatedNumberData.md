# ClickSend::PurchaseDedicatedNumberData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dedicated_number** | **String** | The new dedicated number. | [optional] |
| **country** | **String** | The country code of the new dedicated number. | [optional] |
| **price_total** | **String** | The total price of the new dedicated number. | [optional] |
| **_price_setup** | **String** | The setup price of the new dedicated number. | [optional] |
| **_price_monthly** | **String** | The monthly price of the new dedicated number. | [optional] |
| **_currency** | [**Currency**](Currency.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::PurchaseDedicatedNumberData.new(
  dedicated_number: +12282060576,
  country: US,
  price_total: 8.98,
  _price_setup: 22.22,
  _price_monthly: 11.11,
  _currency: null
)
```

