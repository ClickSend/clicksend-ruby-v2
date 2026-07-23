# ClickSend::SendVoiceMessageRequestMessagesInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **source** | **String** |  | [optional][default to &#39;sdk&#39;] |
| **body** | **String** |  | [optional] |
| **to** | **String** |  | [optional] |
| **voice** | **String** |  | [optional] |
| **lang** | **String** |  | [optional] |
| **machine_detection** | **Integer** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SendVoiceMessageRequestMessagesInner.new(
  source: null,
  body: null,
  to: null,
  voice: null,
  lang: null,
  machine_detection: null
)
```

