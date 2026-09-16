# ClickSend::AllowedSenderCountries

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **global** | **Boolean** | Whether this sender type is allowed sending from any country |  |
| **country_codes** | **Array&lt;String&gt;** | List of ISO 3166-1 alpha-2 formatted country codes | [optional] |

## Example

```ruby
require 'clicksend_client'

instance = ClickSend::AllowedSenderCountries.new(
  global: null,
  country_codes: null
)
```

