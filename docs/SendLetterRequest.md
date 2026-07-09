# ClickSend::SendLetterRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **file_url** | **String** |  | [optional] |
| **template_used** | **Integer** |  | [optional] |
| **colour** | **Integer** |  | [optional] |
| **duplex** | **Integer** |  | [optional] |
| **recipients** | [**Array&lt;SendPostcardRequestRecipientsInner&gt;**](SendPostcardRequestRecipientsInner.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SendLetterRequest.new(
  file_url: null,
  template_used: null,
  colour: null,
  duplex: null,
  recipients: null
)
```

