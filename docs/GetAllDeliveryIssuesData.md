# ClickSend::GetAllDeliveryIssuesData

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
| **data** | [**Array&lt;DeliveryIssue&gt;**](DeliveryIssue.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::GetAllDeliveryIssuesData.new(
  total: 2,
  per_page: 15,
  current_page: 1,
  last_page: 1,
  next_page_url: null,
  prev_page_url: null,
  from: 1,
  to: 2,
  data: [{&quot;issue_id&quot;:1,&quot;user_id&quot;:3820,&quot;message_id&quot;:&quot;B388828B-AD46-4366-8AD3-0305FF5E3FE5&quot;,&quot;type&quot;:&quot;sms&quot;,&quot;description&quot;:&quot;this is a test.&quot;,&quot;client_comments&quot;:null,&quot;support_comments&quot;:null,&quot;status&quot;:null,&quot;date_added&quot;:1481610495,&quot;resolved&quot;:0,&quot;email_address&quot;:&quot;test@user.com&quot;},{&quot;issue_id&quot;:2,&quot;user_id&quot;:3820,&quot;message_id&quot;:&quot;90396A38-146B-46C4-A455-675F620C2E05&quot;,&quot;type&quot;:&quot;sms&quot;,&quot;description&quot;:&quot;this is a test.&quot;,&quot;client_comments&quot;:null,&quot;support_comments&quot;:null,&quot;status&quot;:null,&quot;date_added&quot;:1481610495,&quot;resolved&quot;:0,&quot;email_address&quot;:&quot;test@user.com&quot;},{&quot;issue_id&quot;:3,&quot;user_id&quot;:3820,&quot;message_id&quot;:&quot;4ECFB6CB-0300-45EC-96E1-5AB189432AF5&quot;,&quot;type&quot;:&quot;sms&quot;,&quot;description&quot;:&quot;this is a test.&quot;,&quot;client_comments&quot;:null,&quot;support_comments&quot;:null,&quot;status&quot;:null,&quot;date_added&quot;:1481611389,&quot;resolved&quot;:0,&quot;email_address&quot;:&quot;test@user.com&quot;}]
)
```

