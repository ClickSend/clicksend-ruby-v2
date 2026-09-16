# ClickSend::Country

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **code** | **String** | The country code. | [optional] |
| **value** | **String** | The country name. | [optional] |

## Example

```ruby
require 'clicksend_client'

instance = ClickSend::Country.new(
  code: AU,
  value: Australia
)
```

