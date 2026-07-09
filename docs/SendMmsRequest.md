# ClickSend::SendMmsRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **media_file** | **String** |  | [optional] |
| **messages** | [**Array&lt;SendMmsRequestMessagesInner&gt;**](SendMmsRequestMessagesInner.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SendMmsRequest.new(
  media_file: null,
  messages: null
)
```

