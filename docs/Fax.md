# ClickSend::Fax

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **user_id** | **Integer** | The ID of the user. | [optional] |
| **subaccount_id** | **Integer** | The ID of the subaccount. | [optional] |
| **list_id** | **Integer** | The ID of the list. | [optional] |
| **message_id** | **String** | The ID of the message. | [optional] |
| **to** | **String** | The recipient&#39;s phone number. | [optional] |
| **from** | **String** | The sender&#39;s phone number. | [optional] |
| **carrier** | **String** | The carrier associated with the message. | [optional] |
| **country** | **String** | The country code. | [optional] |
| **custom_string** | **String** | A custom string associated with the message. | [optional] |
| **schedule** | **String** | The scheduled time for sending the message. | [optional] |
| **message_pages** | **Integer** | The number of pages in the message. | [optional] |
| **message_price** | **String** | The price of the message. | [optional] |
| **status_code** | **String** | The status code of the message. | [optional] |
| **status_text** | **String** | The status text of the message. | [optional] |
| **date_added** | **Integer** | The date when the message was added. | [optional] |
| **from_email** | **String** | The sender&#39;s email address. | [optional] |
| **_file_url** | **String** | The URL of the file associated with the message. | [optional] |
| **status** | **String** | The status of the message. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::Fax.new(
  user_id: 1,
  subaccount_id: 1,
  list_id: null,
  message_id: 6BBEB11E-CAA6-4B04-8537-63619F3D6B37,
  to: +61261111122,
  from: +61298441484,
  carrier: ,
  country: AU,
  custom_string: custom_string,
  schedule: 1436874701,
  message_pages: 6,
  message_price: 13.2000,
  status_code: 201,
  status_text: Sent,
  date_added: 1457504350,
  from_email: john@doe.com,
  _file_url: https://rest.clicksend.com/files/98DDA1A4-8A74-4831-8FAF-CC4B4EBD8241.pdf,
  status: SUCCESS
)
```

