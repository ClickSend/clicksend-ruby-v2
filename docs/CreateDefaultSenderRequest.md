# ClickSend::CreateDefaultSenderRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **country_code** | **String** | The country code of the recipient. Must be a valid ISO 3166-1 alpha-2 country code. |  |
| **product_type** | **String** | The type of product for the assignment. Support for additional types coming soon. |  |
| **default_sender_strategies** | [**Array&lt;CreateDefaultSenderRequestDefaultSenderStrategiesInner&gt;**](CreateDefaultSenderRequestDefaultSenderStrategiesInner.md) | Array detailing sender strategies. Must contain exactly 1 element. Multiple strategies support coming soon. |  |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CreateDefaultSenderRequest.new(
  country_code: AU,
  product_type: null,
  default_sender_strategies: null
)
```

