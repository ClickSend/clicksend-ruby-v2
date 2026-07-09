# ClickSend::EmailCampaign

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email_campaign_id** | **Integer** | The ID of the email campaign. | [optional] |
| **name** | **String** | The name of the email campaign. | [optional] |
| **user_id** | **Integer** | The ID of the user who created the email campaign. | [optional] |
| **subaccount_id** | **Integer** | The ID of the subaccount associated with the email campaign. | [optional] |
| **subject** | **String** | The subject of the email campaign. | [optional] |
| **list_id** | **Integer** | The ID of the email list associated with the campaign. | [optional] |
| **from_email_address_id** | **Integer** | The ID of the sender&#39;s email address. | [optional] |
| **from_name** | **String** | The name of the sender. | [optional] |
| **template_id** | **Integer** | The ID of the email template used in the campaign. | [optional] |
| **schedule** | **String** | The schedule for sending the email campaign. | [optional] |
| **status** | **String** | The status of the email campaign (e.g., Sent, Scheduled, Draft). | [optional] |
| **date_added** | **String** | The date when the email campaign was added. | [optional] |
| **custom_string** | **String** | A custom string associated with the email campaign. | [optional] |
| **send_count** | **Integer** | The count of emails sent in the campaign. | [optional] |
| **open_count** | **Integer** | The count of emails opened in the campaign. | [optional] |
| **click_count** | **Integer** | The count of links clicked in the campaign. | [optional] |
| **hard_bounce_count** | **Integer** | The count of hard bounces in the campaign. | [optional] |
| **soft_bounce_count** | **Integer** | The count of soft bounces in the campaign. | [optional] |
| **abuse_count** | **Integer** | The count of abuse complaints in the campaign. | [optional] |
| **unsubscribe_count** | **Integer** | The count of unsubscribes in the campaign. | [optional] |
| **body** | **String** | The body of the email campaign. | [optional] |
| **body_plain_text** | **String** | The plain text body of the email campaign. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::EmailCampaign.new(
  email_campaign_id: 64,
  name: test email,
  user_id: 1201,
  subaccount_id: 1038,
  subject: My test subject,
  list_id: 443,
  from_email_address_id: 2,
  from_name: Test name,
  template_id: 24,
  schedule: ,
  status: Sent,
  date_added: 1455586793,
  custom_string: ,
  send_count: 0,
  open_count: 5,
  click_count: 0,
  hard_bounce_count: 0,
  soft_bounce_count: 0,
  abuse_count: 0,
  unsubscribe_count: 0,
  body: test body,
  body_plain_text: test body
)
```

