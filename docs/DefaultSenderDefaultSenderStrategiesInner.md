# ClickSend::DefaultSenderDefaultSenderStrategiesInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **sender_type** | **String** | Type of the sender. |  |
| **sender_id** | **String** | Identifier for the sender. Must be between 3-20 characters. |  |
| **sender_country_code** | **String** | ISO 3166-1 alpha-2 formatted country code. | [optional] |
| **priority** | **Integer** | Priority level of the sender in the strategy. Must be a positive integer. |  |
| **status** | **String** | Status of the sender in the strategy. |  |
| **note** | **String** | Note providing additional context about the sender. Maximum length of 200 characters. Optional. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::DefaultSenderDefaultSenderStrategiesInner.new(
  sender_type: alpha_tag,
  sender_id: ClickSend,
  sender_country_code: null,
  priority: 1,
  status: ENABLED,
  note: This is a test default sender
)
```

