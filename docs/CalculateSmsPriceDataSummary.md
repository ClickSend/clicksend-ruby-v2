# ClickSend::CalculateSmsPriceDataSummary

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **test_message** | **String** | This parameter is used for internal developers. This is used when your account is in trial period. | [optional] |
| **countries** | [**Array&lt;CalculateSmsPriceDataSummaryCountriesInner&gt;**](CalculateSmsPriceDataSummaryCountriesInner.md) | The list of countries of the receipients in two-letter format (e.g. US, UK, AU, NZ, etc). | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CalculateSmsPriceDataSummary.new(
  test_message: null,
  countries: null
)
```

