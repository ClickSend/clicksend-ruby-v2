# ClickSend::GetAllDeliveryIssues

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP status code of the response. | [optional] |
| **response_code** | **String** | The response code indicating the status of the operation. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | [**Array&lt;DeliveryIssue&gt;**](DeliveryIssue.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::GetAllDeliveryIssues.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: Here is your result.,
  data: [{&quot;issue_id&quot;:1,&quot;user_id&quot;:3820,&quot;message_id&quot;:&quot;B388828B-AD46-4366-8AD3-0305FF5E3FE5&quot;,&quot;type&quot;:&quot;sms&quot;,&quot;description&quot;:&quot;this is a test.&quot;,&quot;client_comments&quot;:null,&quot;support_comments&quot;:null,&quot;status&quot;:null,&quot;date_added&quot;:1481610495,&quot;resolved&quot;:0,&quot;email_address&quot;:&quot;test@user.com&quot;},{&quot;issue_id&quot;:2,&quot;user_id&quot;:3820,&quot;message_id&quot;:&quot;90396A38-146B-46C4-A455-675F620C2E05&quot;,&quot;type&quot;:&quot;sms&quot;,&quot;description&quot;:&quot;this is a test.&quot;,&quot;client_comments&quot;:null,&quot;support_comments&quot;:null,&quot;status&quot;:null,&quot;date_added&quot;:1481610495,&quot;resolved&quot;:0,&quot;email_address&quot;:&quot;test@user.com&quot;},{&quot;issue_id&quot;:3,&quot;user_id&quot;:3820,&quot;message_id&quot;:&quot;4ECFB6CB-0300-45EC-96E1-5AB189432AF5&quot;,&quot;type&quot;:&quot;sms&quot;,&quot;description&quot;:&quot;this is a test.&quot;,&quot;client_comments&quot;:null,&quot;support_comments&quot;:null,&quot;status&quot;:null,&quot;date_added&quot;:1481611389,&quot;resolved&quot;:0,&quot;email_address&quot;:&quot;test@user.com&quot;}]
)
```

