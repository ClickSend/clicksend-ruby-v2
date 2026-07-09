# ClickSend::PostcardRecipient

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
| **letter_file_name** | **String** | The filename of the letter file. | [optional] |
| **schedule** | **Integer** | The schedule timestamp of the message. | [optional] |
| **ip_address** | **String** | The IP address associated with the message. | [optional] |
| **source** | **String** | The source of the message. | [optional] |
| **post_price** | **Integer** | The price of posting the message. | [optional] |
| **priority** | **Integer** | The priority of the message. | [optional] |
| **status** | **String** | The status of the message. | [optional] |
| **date_added** | **Integer** | The timestamp when the message was added. | [optional] |
| **_file_url** | **String** | The URL of the file associated with the message. | [optional] |
| **_return_address** | [**PostcardRecipientReturnAddress**](PostcardRecipientReturnAddress.md) |  | [optional] |
| **_api_username** | **String** | The API username associated with the message. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::PostcardRecipient.new(
  user_id: 1,
  subaccount_id: 13,
  message_id: C8CAA97A-905A-4A31-99CB-A92C7BA05A97,
  address_name: John Smith,
  address_line_1: Address 1,
  address_line_2: ,
  address_city: CITY,
  address_state: State,
  address_postal_code: 123456,
  address_country: AU,
  return_address_id: 1,
  letter_file_name: 6A559A74-486D-4012-84D7-F3FE11904CB1.pdf,
  schedule: 1482473172,
  ip_address: 127.0.0.1,
  source: .rest.v3,
  post_price: 11,
  priority: 32,
  status: SUCCESS,
  date_added: 1482473172,
  _file_url: https://rest.clicksend.com/files/6A559A74-486D-4012-84D7-F3FE11904CB1.pdf,
  _return_address: null,
  _api_username: johndoe
)
```

