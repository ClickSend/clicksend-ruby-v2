# ClickSend::CreateReturnAddressRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **address_name** | **String** |  | [optional] |
| **address_line_1** | **String** |  | [optional] |
| **address_line_2** | **String** |  | [optional] |
| **address_city** | **String** |  | [optional] |
| **address_postal_code** | **String** |  | [optional] |
| **address_country** | **String** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CreateReturnAddressRequest.new(
  address_name: null,
  address_line_1: null,
  address_line_2: null,
  address_city: null,
  address_postal_code: null,
  address_country: null
)
```

