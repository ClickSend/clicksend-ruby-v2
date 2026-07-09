# ClickSend::PostReturnAddress

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **return_address_id** | **Integer** | The ID of the return address. | [optional] |
| **user_id** | **Integer** | The ID of the user associated with the return address. | [optional] |
| **address_name** | **String** | The name associated with the return address. | [optional] |
| **address_line_1** | **String** | The first line of the return address. | [optional] |
| **address_line_2** | **String** | The second line of the return address (optional). | [optional] |
| **address_city** | **String** | The city of the return address. | [optional] |
| **address_state** | **String** | The state or region of the return address. | [optional] |
| **address_postal_code** | **String** | The postal code or ZIP code of the return address. | [optional] |
| **address_country** | **String** | The country of the return address. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::PostReturnAddress.new(
  return_address_id: 4,
  user_id: 1,
  address_name: My Address,
  address_line_1: Maritime Avenue,
  address_line_2: ,
  address_city: Flynn,
  address_state: WA,
  address_postal_code: 6302,
  address_country: AU
)
```

