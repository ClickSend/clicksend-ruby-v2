# ClickSend::ViewAllEmailCampaignsData

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
| **data** | [**Array&lt;EmailCampaign&gt;**](EmailCampaign.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewAllEmailCampaignsData.new(
  total: 2,
  per_page: 15,
  current_page: 1,
  last_page: 1,
  next_page_url: null,
  prev_page_url: null,
  from: 1,
  to: 2,
  data: [{&quot;email_campaign_id&quot;:64,&quot;name&quot;:&quot;test email&quot;,&quot;user_id&quot;:1201,&quot;subaccount_id&quot;:1038,&quot;subject&quot;:&quot;My test subject&quot;,&quot;list_id&quot;:443,&quot;from_email_address_id&quot;:2,&quot;from_name&quot;:&quot;Test name&quot;,&quot;template_id&quot;:24,&quot;schedule&quot;:&quot;&quot;,&quot;status&quot;:&quot;Sent&quot;,&quot;date_added&quot;:&quot;1455586793&quot;,&quot;custom_string&quot;:&quot;&quot;,&quot;send_count&quot;:0,&quot;open_count&quot;:5,&quot;click_count&quot;:0,&quot;hard_bounce_count&quot;:0,&quot;soft_bounce_count&quot;:0,&quot;abuse_count&quot;:0,&quot;unsubscribe_count&quot;:0},{&quot;email_campaign_id&quot;:65,&quot;name&quot;:&quot;test email&quot;,&quot;user_id&quot;:1201,&quot;subaccount_id&quot;:1038,&quot;subject&quot;:&quot;My test subject&quot;,&quot;list_id&quot;:443,&quot;from_email_address_id&quot;:2,&quot;from_name&quot;:&quot;Test name&quot;,&quot;template_id&quot;:24,&quot;schedule&quot;:&quot;&quot;,&quot;status&quot;:&quot;Queued&quot;,&quot;date_added&quot;:&quot;1455586848&quot;,&quot;custom_string&quot;:&quot;&quot;,&quot;send_count&quot;:0,&quot;open_count&quot;:5,&quot;click_count&quot;:0,&quot;hard_bounce_count&quot;:0,&quot;soft_bounce_count&quot;:0,&quot;abuse_count&quot;:0,&quot;unsubscribe_count&quot;:0}]
)
```

