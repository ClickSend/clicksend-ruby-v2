# ClickSend::Mms

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **list_id** | **String** | The ID of the list (if applicable). | [optional] |
| **contact_id** | **Integer** | The ID of the contact. | [optional] |
| **message_id** | **String** | The ID of the message. | [optional] |
| **to** | **String** | The recipient of the message. | [optional] |
| **subject** | **String** | The subject of the message. | [optional] |
| **from** | **String** | The sender of the message. | [optional] |
| **body** | **String** | The body of the message. | [optional] |
| **country** | **String** | The country code. | [optional] |
| **custom_string** | **String** | Custom string associated with the message. | [optional] |
| **schedule** | **String** | The schedule time of the message. | [optional] |
| **message_parts** | **Integer** | The number of parts the message was split into. | [optional] |
| **message_price** | **String** | The price of the message. | [optional] |
| **_media_file_url** | **String** | The URL of the media file attached to the message. | [optional] |
| **status** | **String** | The status of the message. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::Mms.new(
  list_id: null,
  contact_id: 4,
  message_id: D7A79BF1-4806-43F8-8339-6B9F8385D9A4,
  to: +61298444214,
  subject: This is a subject,
  from: +61411111111,
  body: John This is a test message.,
  country: AU,
  custom_string: ,
  schedule: ,
  message_parts: 1,
  message_price: 2.4200,
  _media_file_url: https://yourdomain.com/tpLaX6A.gif,
  status: SUCCESS
)
```

