# ClickSend::CurrentPaymentInfoData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **display_number** | **String** | The credit card number. | [optional] |
| **expiry_month** | **Integer** | The credit card expiry month. | [optional] |
| **expiry_year** | **Integer** | The credit card expiry year. | [optional] |
| **name** | **String** | The credit card name. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CurrentPaymentInfoData.new(
  display_number: XXXX-XXXX-XXXX-0000,
  expiry_month: 1,
  expiry_year: 2020,
  name: Roland Robot
)
```

