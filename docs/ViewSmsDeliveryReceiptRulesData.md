# ClickSend::ViewSmsDeliveryReceiptRulesData

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
| **data** | [**Array&lt;SmsDeliveryReceiptRule&gt;**](SmsDeliveryReceiptRule.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewSmsDeliveryReceiptRulesData.new(
  total: 2,
  per_page: 15,
  current_page: 1,
  last_page: 1,
  next_page_url: null,
  prev_page_url: null,
  from: 1,
  to: 2,
  data: [{&quot;receipt_rule_id&quot;:5,&quot;rule_name&quot;:&quot;My Rule&quot;,&quot;match_type&quot;:0,&quot;action&quot;:&quot;EMAIL_FIXED&quot;,&quot;action_address&quot;:&quot;john@doe.com&quot;,&quot;enabled&quot;:0},{&quot;receipt_rule_id&quot;:6,&quot;rule_name&quot;:&quot;My Rule&quot;,&quot;match_type&quot;:0,&quot;action&quot;:&quot;EMAIL_FIXED&quot;,&quot;action_address&quot;:&quot;john@doe.com&quot;,&quot;enabled&quot;:1},{&quot;receipt_rule_id&quot;:7,&quot;rule_name&quot;:&quot;My Rule&quot;,&quot;match_type&quot;:0,&quot;action&quot;:&quot;EMAIL_FIXED&quot;,&quot;action_address&quot;:&quot;john@doe.com&quot;,&quot;enabled&quot;:1},{&quot;receipt_rule_id&quot;:8,&quot;rule_name&quot;:&quot;My Rule&quot;,&quot;match_type&quot;:0,&quot;action&quot;:&quot;SMS&quot;,&quot;action_address&quot;:&quot;+61298441484&quot;,&quot;enabled&quot;:1},{&quot;receipt_rule_id&quot;:9,&quot;rule_name&quot;:&quot;My Rule&quot;,&quot;match_type&quot;:0,&quot;action&quot;:&quot;URL&quot;,&quot;action_address&quot;:&quot;+61298441485&quot;,&quot;enabled&quot;:1}]
)
```

