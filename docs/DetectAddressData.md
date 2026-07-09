# ClickSend::DetectAddressData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **address_name** | **String** | The recipient&#39;s name. | [optional] |
| **address_line_1** | **String** | The first line of the recipient&#39;s address. | [optional] |
| **address_line_2** | **String** | The second line of the recipient&#39;s address (optional). | [optional] |
| **address_city** | **String** | The city of the recipient&#39;s address. | [optional] |
| **address_state** | **String** | The state or region of the recipient&#39;s address. | [optional] |
| **address_postal_code** | **String** | The postal code or ZIP code of the recipient&#39;s address. | [optional] |
| **address_country** | **String** | The country of the recipient&#39;s address. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::DetectAddressData.new(
  address_name: John Doe,
  address_line_1: 123 Main Street,
  address_line_2: ,
  address_city: Perth,
  address_state: WA,
  address_postal_code: 6000,
  address_country: AU
)
```

