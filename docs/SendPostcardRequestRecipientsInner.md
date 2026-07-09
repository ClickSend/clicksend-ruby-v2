# ClickSend::SendPostcardRequestRecipientsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **address_name** | **String** |  | [optional] |
| **address_city** | **String** |  | [optional] |
| **address_state** | **String** |  | [optional] |
| **address_postal_code** | **String** |  | [optional] |
| **address_country** | **String** |  | [optional] |
| **address_line_1** | **String** |  | [optional] |
| **return_address_id** | **String** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SendPostcardRequestRecipientsInner.new(
  address_name: null,
  address_city: null,
  address_state: null,
  address_postal_code: null,
  address_country: null,
  address_line_1: null,
  return_address_id: null
)
```

