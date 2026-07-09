# ClickSend::ListCountriesDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** | The id of the country. | [optional] |
| **name** | **String** | The name of the country. | [optional] |
| **code** | **String** | The code of the country. | [optional] |
| **region** | **String** | The region of the country. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ListCountriesDataInner.new(
  id: 1,
  name: Australia,
  code: AU,
  region: Oceania
)
```

