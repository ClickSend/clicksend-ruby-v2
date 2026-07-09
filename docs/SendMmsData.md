# ClickSend::SendMmsData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_price** | **Float** | The total price of the MMS messages. | [optional] |
| **total_count** | **Integer** | The total count of the MMS messages. | [optional] |
| **queued_count** | **Integer** | The count of the queued MMS messages. | [optional] |
| **messages** | [**Array&lt;Mms&gt;**](Mms.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SendMmsData.new(
  total_price: 13.2,
  total_count: 1,
  queued_count: 1,
  messages: null
)
```

