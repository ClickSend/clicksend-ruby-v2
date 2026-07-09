# ClickSend::VerifyAllowedEmailAddressRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **to** | [**Array&lt;SendEmailRequestToInner&gt;**](SendEmailRequestToInner.md) |  | [optional] |
| **from** | [**SendEmailVerificationTokenRequestFrom**](SendEmailVerificationTokenRequestFrom.md) |  | [optional] |
| **subject** | **String** |  | [optional] |
| **body** | **String** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::VerifyAllowedEmailAddressRequest.new(
  to: null,
  from: null,
  subject: null,
  body: null
)
```

