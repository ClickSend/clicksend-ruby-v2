# ClickSend::SendFaxData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_price** | **Float** | The total price of the fax. | [optional] |
| **total_count** | **Integer** | The total count of the fax. | [optional] |
| **queued_count** | **Integer** | The count of the queued fax. | [optional] |
| **messages** | [**Array&lt;Fax&gt;**](Fax.md) | The list of messages that were sent. | [optional] |
| **_currency** | [**Currency**](Currency.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SendFaxData.new(
  total_price: 13.2,
  total_count: 1,
  queued_count: 1,
  messages: null,
  _currency: null
)
```

