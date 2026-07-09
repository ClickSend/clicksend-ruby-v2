# ClickSend::SendVoiceMessageData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_price** | **Float** | The total price of the message. | [optional] |
| **total_count** | **Float** | The total count of the message. | [optional] |
| **queued_count** | **Float** | The count of the queued message. | [optional] |
| **messages** | [**Array&lt;VoiceMessage&gt;**](VoiceMessage.md) |  | [optional] |
| **_currency** | [**Currency**](Currency.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SendVoiceMessageData.new(
  total_price: 0.07,
  total_count: 1,
  queued_count: 1,
  messages: null,
  _currency: null
)
```

