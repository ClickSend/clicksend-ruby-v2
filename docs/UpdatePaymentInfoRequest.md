# ClickSend::UpdatePaymentInfoRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **number** | **String** |  | [optional] |
| **expiry_month** | **Integer** |  | [optional] |
| **expiry_year** | **Integer** |  | [optional] |
| **cvc** | **Integer** |  | [optional] |
| **name** | **String** |  | [optional] |
| **bank_name** | **String** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::UpdatePaymentInfoRequest.new(
  number: null,
  expiry_month: null,
  expiry_year: null,
  cvc: null,
  name: null,
  bank_name: null
)
```

