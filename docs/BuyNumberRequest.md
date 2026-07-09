# ClickSend::BuyNumberRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dedicated_number** | **String** | Phone number to purchase |  |
| **type** | **String** | Service type for the number |  |
| **registration_data** | [**BuyNumberRequestRegistrationData**](BuyNumberRequestRegistrationData.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::BuyNumberRequest.new(
  dedicated_number: +614197651956,
  type: sms,
  registration_data: null
)
```

