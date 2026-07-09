# ClickSend::BuyNumberRequestRegistrationData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **business_name** | **String** | Name of the business (2 - 100 characters) |  |
| **business_address** | **String** | Business address (5 - 150 characters) |  |
| **suburb** | **String** | Suburb/City (2 - 50 characters) |  |
| **postcode** | **String** | Postal code (2 - 20 characters) |  |
| **state** | **String** | State/Province (2 - 50 characters) |  |
| **contact_name** | **String** | Contact person name (2 - 100 characters) |  |
| **contact_number** | **String** | Contact phone number (valid local or international phone number) |  |
| **country** | **String** | Country code (ISO 3166-1 alpha-2) |  |

## Example

```ruby
require 'clicksend'

instance = ClickSend::BuyNumberRequestRegistrationData.new(
  business_name: ABD,
  business_address: 242 Exhibition Street,
  suburb: Melbourne,
  postcode: 3000,
  state: Victoria,
  contact_name: ABD,
  contact_number: +614197651956,
  country: AU
)
```

