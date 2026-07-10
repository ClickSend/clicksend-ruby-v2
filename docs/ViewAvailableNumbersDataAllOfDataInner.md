# ClickSend::ViewAvailableNumbersDataAllOfDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **country** | **String** | The country code of the number. | [optional] |
| **country_name** | **String** | The country name of the number. | [optional] |
| **dedicated_number** | **String** | The dedicated number. | [optional] |
| **price_setup** | **String** | The setup price of the number. | [optional] |
| **price_monthly** | **String** | The monthly price of the number. | [optional] |
| **price_total** | **String** | The total price of the number. | [optional] |
| **address_requirement** | **String** | The address requirement for the number.  &lt;br&gt; &#x60;local&#x60;: requires an address that corresponds  to the phone number&#39;s prefix. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewAvailableNumbersDataAllOfDataInner.new(
  country: null,
  country_name: null,
  dedicated_number: null,
  price_setup: null,
  price_monthly: null,
  price_total: null,
  address_requirement: null
)
```

