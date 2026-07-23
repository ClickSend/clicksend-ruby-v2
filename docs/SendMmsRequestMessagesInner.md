# ClickSend::SendMmsRequestMessagesInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **source** | **String** |  | [optional][default to &#39;sdk&#39;] |
| **to** | **String** |  | [optional] |
| **from** | **String** |  | [optional] |
| **subject** | **String** |  | [optional] |
| **body** | **String** |  | [optional] |
| **schedule** | **Integer** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SendMmsRequestMessagesInner.new(
  source: null,
  to: null,
  from: null,
  subject: null,
  body: null,
  schedule: null
)
```

