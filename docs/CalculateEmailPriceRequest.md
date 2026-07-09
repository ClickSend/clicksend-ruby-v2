# ClickSend::CalculateEmailPriceRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **to** | [**Array&lt;SendEmailRequestToInner&gt;**](SendEmailRequestToInner.md) |  | [optional] |
| **from** | [**SendEmailRequestFrom**](SendEmailRequestFrom.md) |  | [optional] |
| **subject** | **String** |  | [optional] |
| **body** | **String** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CalculateEmailPriceRequest.new(
  to: null,
  from: null,
  subject: null,
  body: null
)
```

