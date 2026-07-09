# ClickSend::ViewLetterHistoryData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total** | **Integer** | The total number of items available for viewing. | [optional] |
| **per_page** | **Integer** | The number of items returned per page. This is specified in the limit parameter. You can have 100 items at maximum, and 15 at minimum. | [optional] |
| **current_page** | **Integer** | The current page number. | [optional] |
| **last_page** | **Integer** | The last page number. | [optional] |
| **next_page_url** | **String** | A URL of the next page. It will return **null** if there’s no next page. | [optional] |
| **prev_page_url** | **String** | A URL of the previous page. It will return **null** if there’s no previous page. | [optional] |
| **from** | **Integer** | The number of the first result in the current page. | [optional] |
| **to** | **Integer** | The number of the last result in the current page. | [optional] |
| **data** | [**Array&lt;Recipient&gt;**](Recipient.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewLetterHistoryData.new(
  total: 2,
  per_page: 15,
  current_page: 1,
  last_page: 1,
  next_page_url: null,
  prev_page_url: null,
  from: 1,
  to: 2,
  data: [{&quot;user_id&quot;:1,&quot;subaccount_id&quot;:1,&quot;message_id&quot;:&quot;06FAD39C-78FD-4D2F-B606-9846D1979F35&quot;,&quot;address_name&quot;:&quot;John Smith&quot;,&quot;address_line_1&quot;:&quot;131&quot;,&quot;address_line_2&quot;:&quot;Scheuvront Drive&quot;,&quot;address_city&quot;:&quot;DENVER&quot;,&quot;address_state&quot;:&quot;CO&quot;,&quot;address_postal_code&quot;:80202,&quot;address_country&quot;:&quot;AU&quot;,&quot;return_address_id&quot;:1,&quot;schedule&quot;:1449573604,&quot;post_pages&quot;:3,&quot;post_price&quot;:&quot;1.8700&quot;,&quot;priority_post&quot;:0,&quot;date_added&quot;:1449662203,&quot;status&quot;:&quot;SUCCESS&quot;}]
)
```

