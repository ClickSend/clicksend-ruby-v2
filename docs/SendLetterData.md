# ClickSend::SendLetterData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **recipients** | [**Array&lt;Recipient&gt;**](Recipient.md) |  | [optional] |
| **_currency** | [**Currency**](Currency.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SendLetterData.new(
  recipients: null,
  _currency: null
)
```

