# ClickSend::EmailCampaignHistory

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email_campaign_id** | **Integer** | The ID of the email campaign. | [optional] |
| **from_name** | **String** | The name of the sender. | [optional] |
| **from_address** | **String** | The email address of the sender. | [optional] |
| **to_name** | **String** | The name of the recipient. | [optional] |
| **to_address** | **String** | The email address of the recipient. | [optional] |
| **contact_id** | **Integer** | The ID of the contact associated with the email. | [optional] |
| **subject** | **String** | The subject of the email. | [optional] |
| **message_id** | **String** | The unique ID of the email message. | [optional] |
| **processed_at** | **String** | The date and time when the email was processed. | [optional] |
| **status** | **String** | The status of the email (e.g., SpamReport, Sent). | [optional] |
| **open_count** | **Integer** | The count of times the email was opened. | [optional] |
| **click_count** | **Integer** | The count of times links in the email were clicked. | [optional] |
| **hard_bounce_count** | **Integer** | The count of hard bounces for the email. | [optional] |
| **soft_bounce_count** | **Integer** | The count of soft bounces for the email. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::EmailCampaignHistory.new(
  email_campaign_id: 77,
  from_name: test name,
  from_address: 4,
  to_name: test2@test.com,
  to_address: test2@test.com,
  contact_id: 669105,
  subject: test subject,
  message_id: 7CB3227C-7F8C-4A72-A0CB-36283236D99F,
  processed_at: null,
  status: SpamReport,
  open_count: 0,
  click_count: 0,
  hard_bounce_count: 13,
  soft_bounce_count: 1
)
```

