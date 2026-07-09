# ClickSend::SendEmailRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **to** | [**Array&lt;SendEmailRequestToInner&gt;**](SendEmailRequestToInner.md) |  | [optional] |
| **from** | [**SendEmailRequestFrom**](SendEmailRequestFrom.md) |  | [optional] |
| **subject** | **String** |  | [optional] |
| **body** | **String** |  | [optional] |
| **attachments** | [**Array&lt;SendEmailRequestAttachmentsInner&gt;**](SendEmailRequestAttachmentsInner.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SendEmailRequest.new(
  to: null,
  from: null,
  subject: null,
  body: null,
  attachments: null
)
```

