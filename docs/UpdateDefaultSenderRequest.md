# ClickSend::UpdateDefaultSenderRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **default_sender_strategies** | [**Array&lt;CreateDefaultSenderRequestDefaultSenderStrategiesInner&gt;**](CreateDefaultSenderRequestDefaultSenderStrategiesInner.md) | Array detailing sender strategies. Must contain exactly 1 element. Multiple strategies support coming soon. |  |

## Example

```ruby
require 'clicksend'

instance = ClickSend::UpdateDefaultSenderRequest.new(
  default_sender_strategies: null
)
```

