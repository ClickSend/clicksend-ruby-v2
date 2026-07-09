# ClickSend::CalculateLetterPriceData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_price** | **Float** | The total price of the letter. | [optional] |
| **total_cost** | **Float** | The total cost of the letter. | [optional] |
| **recipients** | [**Array&lt;Recipient&gt;**](Recipient.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CalculateLetterPriceData.new(
  total_price: 1.87,
  total_cost: 1,
  recipients: [{&quot;user_id&quot;:1,&quot;subaccount_id&quot;:1,&quot;message_id&quot;:&quot;06FAD39C-78FD-4D2F-B606-9846D1979F35&quot;,&quot;address_name&quot;:&quot;John Smith&quot;,&quot;address_line_1&quot;:&quot;131&quot;,&quot;address_line_2&quot;:&quot;Scheuvront Drive&quot;,&quot;address_city&quot;:&quot;DENVER&quot;,&quot;address_state&quot;:&quot;CO&quot;,&quot;address_postal_code&quot;:80202,&quot;address_country&quot;:&quot;AU&quot;,&quot;return_address_id&quot;:1,&quot;schedule&quot;:1449573604,&quot;post_pages&quot;:3,&quot;post_price&quot;:&quot;1.8700&quot;,&quot;priority_post&quot;:0,&quot;date_added&quot;:1449662203,&quot;status&quot;:&quot;SUCCESS&quot;}]
)
```

