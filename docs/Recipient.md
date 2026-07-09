# ClickSend::Recipient

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **user_id** | **Integer** | The ID of the user. | [optional] |
| **subaccount_id** | **Integer** | The ID of the subaccount. | [optional] |
| **message_id** | **String** | The ID of the message. | [optional] |
| **address_name** | **String** | The name associated with the address. | [optional] |
| **address_line_1** | **String** | The first line of the address. | [optional] |
| **address_line_2** | **String** | The second line of the address. | [optional] |
| **address_city** | **String** | The city of the address. | [optional] |
| **address_state** | **String** | The state of the address. | [optional] |
| **address_postal_code** | **String** | The postal code of the address. | [optional] |
| **address_country** | **String** | The country code of the address. | [optional] |
| **return_address_id** | **Integer** | The ID of the return address. | [optional] |
| **custom_string** | **String** | A custom string associated with the message. | [optional] |
| **schedule** | **Integer** | The schedule timestamp of the message. | [optional] |
| **source** | **String** | The source of the message. | [optional] |
| **colour** | **Integer** | The color setting of the message. | [optional] |
| **duplex** | **Integer** | Whether the message is set to duplex printing. | [optional] |
| **post_pages** | **Integer** | The number of pages in the postal message. | [optional] |
| **post_price** | **String** | The price of the postal message. | [optional] |
| **priority_post** | **Integer** | Whether the postal message is set to priority. | [optional] |
| **date_added** | **Integer** | The timestamp when the message was added. | [optional] |
| **status** | **String** | The status of the message. | [optional] |
| **_file_url** | **String** | The URL of the file associated with the message. | [optional] |
| **_return_address** | [**PostcardRecipientReturnAddress**](PostcardRecipientReturnAddress.md) |  | [optional] |
| **_api_username** | **String** | The API username associated with the message. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::Recipient.new(
  user_id: 1,
  subaccount_id: 1,
  message_id: A00A1066-BBAE-432B-9B2D-E88969B12C46,
  address_name: John Smith,
  address_line_1: Address 1,
  address_line_2: ,
  address_city: CITY,
  address_state: State,
  address_postal_code: 123456,
  address_country: AU,
  return_address_id: 1,
  custom_string: kn0ChLhwn6,
  schedule: 1449573604,
  source: .rest.v3,
  colour: 1,
  duplex: 0,
  post_pages: 7,
  post_price: 13.4200,
  priority_post: 0,
  date_added: 1459131623,
  status: SUCCESS,
  _file_url: http://yourdomain.com/file.pdf,
  _return_address: null,
  _api_username: my_api_username
)
```

