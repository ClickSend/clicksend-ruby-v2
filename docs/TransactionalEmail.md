# ClickSend::TransactionalEmail

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **user_id** | **Integer** | The ID of the user. | [optional] |
| **subaccount_id** | **Integer** | The ID of the subaccount. | [optional] |
| **from_email_address_id** | **Integer** | The ID of the from email address. | [optional] |
| **from_name** | **String** | The name of the sender. | [optional] |
| **to** | [**Array&lt;SendEmailRequestToInner&gt;**](SendEmailRequestToInner.md) |  | [optional] |
| **cc** | [**Array&lt;SendEmailRequestToInner&gt;**](SendEmailRequestToInner.md) |  | [optional] |
| **bcc** | [**Array&lt;SendEmailRequestToInner&gt;**](SendEmailRequestToInner.md) |  | [optional] |
| **subject** | **String** | The subject of the email. | [optional] |
| **body** | **String** | The HTML body of the email. | [optional] |
| **body_plain_text** | **String** | The plain text body of the email. | [optional] |
| **schedule** | **Integer** | The timestamp indicating the scheduled time of the email. | [optional] |
| **message_id** | **String** | The ID of the email message. | [optional] |
| **status** | **String** | The status of the email. | [optional] |
| **status_text** | **String** | The text description of the email status. | [optional] |
| **soft_bounce_count** | **Integer** | The count of soft bounces. | [optional] |
| **hard_bounce_count** | **Integer** | The count of hard bounces. | [optional] |
| **price** | **String** | The price of the email. | [optional] |
| **date_added** | **Integer** | The timestamp indicating when the email was added. | [optional] |
| **custom_string** | **String** | A custom string. | [optional] |
| **_attachments** | [**Array&lt;Attachment&gt;**](Attachment.md) |  | [optional] |
| **_currency** | [**Currency**](Currency.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::TransactionalEmail.new(
  user_id: 1,
  subaccount_id: 1,
  from_email_address_id: 1,
  from_name: Joanne Doe,
  to: [{&quot;email&quot;:&quot;test@clicksend.com&quot;,&quot;name&quot;:&quot;John Doe&quot;}],
  cc: [{&quot;email&quot;:&quot;test2@clicksend.com&quot;,&quot;name&quot;:&quot;Jane Doe&quot;}],
  bcc: [{&quot;email&quot;:&quot;test3@clicksend.com&quot;,&quot;name&quot;:&quot;Joseph Doe&quot;}],
  subject: Test subject,
  body: Lorem ipsum,
  body_plain_text: Lorem ipsum,
  schedule: 1507018182,
  message_id: 21C632C1-3FCC-4EFF-8191-6079244F0142,
  status: WaitApproval,
  status_text: Accepted for delivery,
  soft_bounce_count: 0,
  hard_bounce_count: 0,
  price: 0.0050,
  date_added: 1507018182,
  custom_string: null,
  _attachments: [{&quot;file_name&quot;:&quot;text.txt&quot;,&quot;content_type&quot;:&quot;text/plain&quot;,&quot;content_disposition&quot;:&quot;attachment&quot;,&quot;content_id&quot;:&quot;text&quot;,&quot;_attachment_file_url&quot;:&quot;https://rest.clicksend.com/files/3C2284DC-7C37-47BA-8C95-3F12A4B987B7.txt&quot;}],
  _currency: null
)
```

