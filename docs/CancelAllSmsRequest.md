# ClickSend::CancelAllSmsRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **custom_string** | **String** | The scheduled messages to cancel with the specified _custom_string_. When you send an SMS, you can add an optional _custom_string_ to it. This parameter allows you to cancel messages that have this _custom_string_.  It&#39;s commonly used for canceling scheduled [SMS campaigns](/messaging/sms-campaigns/). When you send an SMS campaign, the system automatically adds a _custom_string_ to each message, and this parameter lets you cancel only those specific messages. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CancelAllSmsRequest.new(
  custom_string: null
)
```

