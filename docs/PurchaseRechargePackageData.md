# ClickSend::PurchaseRechargePackageData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **user_id** | **Integer** | The ID of the user. | [optional] |
| **amount** | **Integer** | The amount of the package. | [optional] |
| **currency** | **String** | The currency of the package. | [optional] |
| **amount_aud** | **Integer** | The amount of the package in AUD. | [optional] |
| **date** | **Integer** | The timestamp of when the package was purchased. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::PurchaseRechargePackageData.new(
  user_id: 1,
  amount: 50,
  currency: USD,
  amount_aud: null,
  date: 1481610495
)
```

