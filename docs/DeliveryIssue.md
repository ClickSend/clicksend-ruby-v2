# ClickSend::DeliveryIssue

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **issue_id** | **String** | The unique identifier of the delivery issue. | [optional] |
| **user_id** | **Integer** | The unique identifier of the user. | [optional] |
| **message_id** | **String** | The message id of the message. | [optional] |
| **type** | **String** | The type of message, must be one of the following values SMS, MMS, VOICE, EMAIL_MARKETING, EMAIL_TRANSACTIONAL, FAX, POST. | [optional] |
| **description** | **String** | The description of the message. | [optional] |
| **client_comments** | **String** | The user&#39;s comments. | [optional] |
| **support_comments** | **String** | The support&#39;s comments. | [optional] |
| **status** | **String** | The status of the delivery issue. | [optional] |
| **date_added** | **Float** | The date and time the delivery issue was created. | [optional] |
| **resolved** | **Float** | Flag indicating if the delivery issue is resolved. | [optional] |
| **email_address** | **String** | The user&#39;s email address. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::DeliveryIssue.new(
  issue_id: 1,
  user_id: 3820,
  message_id: B388828B-AD46-4366-8AD3-0305FF5E3FE5,
  type: sms,
  description: Test message,
  client_comments: null,
  support_comments: null,
  status: null,
  date_added: 1590000000,
  resolved: 0,
  email_address: johndoe1@awesome.com
)
```

