# ClickSend::SendEmailVerificationTokenRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **to** | [**Array&lt;SendEmailVerificationTokenRequestToInner&gt;**](SendEmailVerificationTokenRequestToInner.md) |  | [optional] |
| **from** | [**SendEmailVerificationTokenRequestFrom**](SendEmailVerificationTokenRequestFrom.md) |  | [optional] |
| **subject** | **String** |  | [optional] |
| **body** | **String** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SendEmailVerificationTokenRequest.new(
  to: null,
  from: null,
  subject: null,
  body: null
)
```

