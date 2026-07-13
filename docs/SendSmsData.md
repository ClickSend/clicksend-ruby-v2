# ClickSend::SendSmsData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_price** | **Float** | The total price of sending the messages. Visit [this page](/#status-codes) for more information. | [optional] |
| **total_count** | **Integer** | The total number of messages sent from the request. | [optional] |
| **queued_count** | **Integer** | The messages will be put in a queue if it goes through the validation process. The validation process checks whether the **Sender ID** is registered or not. Some countries don&#39;t require messages to go through the validation process.  Messages scheduled to be sent right away will be sent immediately. If not, it will be queued. | [optional] |
| **messages** | [**Array&lt;SmsSendSms&gt;**](SmsSendSms.md) | The parameters related to messages. | [optional] |
| **_currency** | [**Currency**](Currency.md) |  | [optional] |
| **blocked_count** | **Integer** | The number of messages unable to be sent. This is often caused by:  - Receipient’s country not enabled for &lt;a href&#x3D;\&quot;https://help.clicksend.com/article/qdavyt16qs-global-sending\&quot;&gt;global sending&lt;/a&gt;.      - **Sender ID** resitriction.      - Number registration restrcition. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SendSmsData.new(
  total_price: 0.0792,
  total_count: 1,
  queued_count: 1,
  messages: [{&quot;direction&quot;:&quot;out&quot;,&quot;date&quot;:&quot;1721099039,&quot;,&quot;to&quot;:&quot;+61411111111&quot;,&quot;body&quot;:&quot;test message&quot;,&quot;from&quot;:&quot;+61431111112&quot;,&quot;schedule&quot;:1721099039,&quot;message_id&quot;:&quot;1ABC3200-C38C-6308-BE4B-C7C51D01DCF0&quot;,&quot;message_parts&quot;:1,&quot;message_price&quot;:&quot;0.0792&quot;,&quot;from_email&quot;:null,&quot;list_id&quot;:null,&quot;custom_string&quot;:&quot;&quot;,&quot;contact_id&quot;:null,&quot;user_id&quot;:123456,&quot;subaccount_id&quot;:123456,&quot;is_shared_system_number&quot;:false,&quot;country&quot;:&quot;AU&quot;,&quot;carrier&quot;:&quot;Vodafone&quot;,&quot;status&quot;:&quot;SUCCESS&quot;}],
  _currency: null,
  blocked_count: 0
)
```

