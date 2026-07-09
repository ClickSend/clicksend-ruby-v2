# ClickSend::SendPostcardData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_price** | **Float** | The total price of the postcard. | [optional] |
| **total_count** | **Integer** | The total count of the postcard. | [optional] |
| **queued_count** | **Integer** | The count of the queued postcard. | [optional] |
| **recipients** | [**Array&lt;PostcardRecipient&gt;**](PostcardRecipient.md) |  | [optional] |
| **_currency** | [**Currency**](Currency.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SendPostcardData.new(
  total_price: 11,
  total_count: 1,
  queued_count: 1,
  recipients: null,
  _currency: null
)
```

