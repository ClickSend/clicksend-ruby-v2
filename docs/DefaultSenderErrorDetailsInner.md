# ClickSend::DefaultSenderErrorDetailsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **field** | **String** | The field that caused the error | [optional] |
| **reason** | **String** | The error message | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::DefaultSenderErrorDetailsInner.new(
  field: default_sender_strategies[0].sender_id,
  reason: Invalid sender ID format
)
```

