# ClickSend::CalculateLetterPriceRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **file_url** | **String** |  | [optional] |
| **template_used** | **Integer** |  | [optional] |
| **duplex** | **Integer** |  | [optional] |
| **colour** | **Integer** |  | [optional] |
| **source** | **String** |  | [optional] |
| **recipients** | [**Array&lt;SendPostcardRequestRecipientsInner&gt;**](SendPostcardRequestRecipientsInner.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CalculateLetterPriceRequest.new(
  file_url: null,
  template_used: null,
  duplex: null,
  colour: null,
  source: null,
  recipients: null
)
```

