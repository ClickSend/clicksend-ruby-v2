# ClickSend::ListCompliantSenderTypes200ResponseDataDataInnerAllowedSenderTypesInnerAllowedSenderCountries

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **global** | **Boolean** | Whether this sender type is allowed sending from any country |  |
| **country_codes** | **Array&lt;String&gt;** | List of ISO 3166-1 alpha-2 formatted country codes | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ListCompliantSenderTypes200ResponseDataDataInnerAllowedSenderTypesInnerAllowedSenderCountries.new(
  global: null,
  country_codes: null
)
```

