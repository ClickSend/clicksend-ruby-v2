# ClickSend::CreateDeliveryIssueData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **issue_id** | **Integer** | The ID of the created delivery issue. | [optional] |
| **user_id** | **Integer** | The ID of the user who created the delivery issue. | [optional] |
| **message_id** | **String** | The ID of the message associated with the delivery issue. | [optional] |
| **type** | **String** | The type of delivery issue. | [optional] |
| **description** | **String** | The description of the delivery issue. | [optional] |
| **date_added** | **Integer** | The timestamp of when the delivery issue was created. | [optional] |
| **email_address** | **String** | The email address associated with the delivery issue. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CreateDeliveryIssueData.new(
  issue_id: 1,
  user_id: 3820,
  message_id: B388828B-AD46-4366-8AD3-0305FF5E3FE5,
  type: sms,
  description: this is a test.,
  date_added: 1481610495,
  email_address: test@user.com
)
```

