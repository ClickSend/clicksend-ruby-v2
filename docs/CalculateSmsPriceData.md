# ClickSend::CalculateSmsPriceData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_price** | **Float** | The total price of sending the messages. Visit [this page](/#status-codes) for more information. | [optional] |
| **total_count** | **Integer** | The total number of messages sent from the request. | [optional] |
| **queued_count** | **Integer** | The messages will be put in a queue if it goes through the validation process. The validation process checks whether the **Sender ID** is registered or not. Some countries don&#39;t require messages to go through the validation process.  Messages scheduled to be sent right away will be sent immediately. If not, it will be queued. | [optional] |
| **messages** | [**Array&lt;Sms&gt;**](Sms.md) | The parameters related to messages. | [optional] |
| **currency** | [**Currency**](Currency.md) |  | [optional] |
| **_summary** | [**CalculateSmsPriceDataSummary**](CalculateSmsPriceDataSummary.md) |  | [optional] |
| **blocked_count** | **Integer** | The number of messages unable to be sent. This is often caused by:  - Receipient’s country not enabled for global sending.      - Sender ID resitriction.      - Number registration restrcition. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CalculateSmsPriceData.new(
  total_price: 0.2264,
  total_count: 1,
  queued_count: 1,
  messages: null,
  currency: null,
  _summary: null,
  blocked_count: null
)
```

