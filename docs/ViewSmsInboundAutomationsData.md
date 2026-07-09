# ClickSend::ViewSmsInboundAutomationsData

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
| **data** | [**Array&lt;SmsInboundRule&gt;**](SmsInboundRule.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewSmsInboundAutomationsData.new(
  total: 2,
  per_page: 15,
  current_page: 1,
  last_page: 1,
  next_page_url: null,
  prev_page_url: null,
  from: 1,
  to: 2,
  data: [{&quot;sms_inbound_rule_id&quot;:1,&quot;dedicated_number&quot;:&quot;+61298441484&quot;,&quot;rule_name&quot;:&quot;My Rule 10&quot;,&quot;message_search_type&quot;:3,&quot;message_search_term&quot;:&quot;My Search Term&quot;,&quot;action&quot;:&quot;CREATE_CONTACT_PLUS_EMAIL&quot;,&quot;action_address&quot;:&quot;430&quot;,&quot;body&quot;:&quot;test@test.com&quot;,&quot;enabled&quot;:1},{&quot;sms_inbound_rule_id&quot;:9,&quot;dedicated_number&quot;:&quot;+61298441484&quot;,&quot;rule_name&quot;:&quot;My Rule 9&quot;,&quot;message_search_type&quot;:3,&quot;message_search_term&quot;:&quot;My Search Term&quot;,&quot;action&quot;:&quot;CREATE_CONTACT&quot;,&quot;action_address&quot;:&quot;john@doe.com&quot;,&quot;body&quot;:null,&quot;enabled&quot;:1}]
)
```

