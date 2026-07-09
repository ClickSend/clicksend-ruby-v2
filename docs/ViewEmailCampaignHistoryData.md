# ClickSend::ViewEmailCampaignHistoryData

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
| **data** | [**Array&lt;EmailCampaignHistory&gt;**](EmailCampaignHistory.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewEmailCampaignHistoryData.new(
  total: 2,
  per_page: 15,
  current_page: 1,
  last_page: 1,
  next_page_url: null,
  prev_page_url: null,
  from: 1,
  to: 2,
  data: [{&quot;email_campaign_id&quot;:77,&quot;from_name&quot;:&quot;test name&quot;,&quot;from_address&quot;:&quot;4&quot;,&quot;to_name&quot;:&quot;test2@test.com&quot;,&quot;to_address&quot;:&quot;test2@test.com&quot;,&quot;contact_id&quot;:669105,&quot;subject&quot;:&quot;test subject&quot;,&quot;message_id&quot;:&quot;7CB3227C-7F8C-4A72-A0CB-36283236D99F&quot;,&quot;processed_at&quot;:null,&quot;status&quot;:&quot;SpamReport&quot;,&quot;open_count&quot;:0,&quot;click_count&quot;:0,&quot;hard_bounce_count&quot;:13,&quot;soft_bounce_count&quot;:1},{&quot;email_campaign_id&quot;:77,&quot;from_name&quot;:&quot;test name&quot;,&quot;from_address&quot;:&quot;4&quot;,&quot;to_name&quot;:&quot;test2@test.com&quot;,&quot;to_address&quot;:&quot;test2@test.com&quot;,&quot;contact_id&quot;:669105,&quot;subject&quot;:&quot;test subject&quot;,&quot;message_id&quot;:&quot;603C5349-5A24-40B4-89ED-F7619F7CC8A3&quot;,&quot;processed_at&quot;:null,&quot;status&quot;:null,&quot;open_count&quot;:0,&quot;click_count&quot;:0,&quot;hard_bounce_count&quot;:0,&quot;soft_bounce_count&quot;:0},{&quot;email_campaign_id&quot;:77,&quot;from_name&quot;:&quot;test name&quot;,&quot;from_address&quot;:&quot;4&quot;,&quot;to_name&quot;:&quot;test2@test.com&quot;,&quot;to_address&quot;:&quot;test2@test.com&quot;,&quot;contact_id&quot;:669105,&quot;subject&quot;:&quot;test subject&quot;,&quot;message_id&quot;:&quot;5C5C0918-B263-42AA-8B5D-9E8ACECC0C64&quot;,&quot;processed_at&quot;:null,&quot;status&quot;:null,&quot;open_count&quot;:0,&quot;click_count&quot;:0,&quot;hard_bounce_count&quot;:0,&quot;soft_bounce_count&quot;:0}]
)
```

