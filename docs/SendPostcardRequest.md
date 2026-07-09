# ClickSend::SendPostcardRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **file_urls** | **Array&lt;String&gt;** |  | [optional] |
| **recipients** | [**Array&lt;SendPostcardRequestRecipientsInner&gt;**](SendPostcardRequestRecipientsInner.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SendPostcardRequest.new(
  file_urls: null,
  recipients: null
)
```

