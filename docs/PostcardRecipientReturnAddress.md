# ClickSend::PostcardRecipientReturnAddress

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **return_address_id** | **Integer** | The ID of the return address. | [optional] |
| **user_id** | **Integer** | The ID of the user associated with the return address. | [optional] |
| **address_name** | **String** | The name associated with the return address. | [optional] |
| **address_line_1** | **String** | The first line of the return address. | [optional] |
| **address_line_2** | **String** | The second line of the return address. | [optional] |
| **address_city** | **String** | The city of the return address. | [optional] |
| **address_state** | **String** | The state of the return address. | [optional] |
| **address_postal_code** | **String** | The postal code of the return address. | [optional] |
| **address_country** | **String** | The country code of the return address. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::PostcardRecipientReturnAddress.new(
  return_address_id: null,
  user_id: null,
  address_name: null,
  address_line_1: null,
  address_line_2: null,
  address_city: null,
  address_state: null,
  address_postal_code: null,
  address_country: null
)
```

