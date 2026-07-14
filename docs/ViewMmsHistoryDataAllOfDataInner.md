# ClickSend::ViewMmsHistoryDataAllOfDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **direction** | **String** | The direction of the message (in or out). | [optional] |
| **date** | **String** | The date of the message. | [optional] |
| **to** | **String** | The recipient of the message. | [optional] |
| **body** | **String** | The body of the message. | [optional] |
| **subject** | **String** | The subject of the message. | [optional] |
| **priority** | **Integer** | The priority of the message. | [optional] |
| **_media_file_url** | **String** | A temporary, signed URL to download the message&#39;s media attachment. | [optional] |
| **status** | **String** | The status of the message. | [optional] |
| **from** | **String** | The sender of the message. | [optional] |
| **schedule** | **String** | The schedule time of the message. | [optional] |
| **date_added** | **Integer** | The Unix timestamp when the message was added. | [optional] |
| **status_code** | **String** | The status code (if applicable). | [optional] |
| **status_text** | **String** | The status text (if applicable). | [optional] |
| **error_code** | **String** | The error code (if applicable). | [optional] |
| **error_text** | **String** | The error text (if applicable). | [optional] |
| **message_id** | **String** | The ID of the message. | [optional] |
| **message_parts** | **String** | The number of parts the message was split into. | [optional] |
| **message_price** | **String** | The price of the message. | [optional] |
| **from_email** | **String** | The email of the sender (if applicable). | [optional] |
| **list_id** | **String** | The ID of the list (if applicable). | [optional] |
| **custom_string** | **String** | Custom string associated with the message. | [optional] |
| **contact_id** | **Integer** | The ID of the contact. | [optional] |
| **user_id** | **Integer** | The ID of the user. | [optional] |
| **subaccount_id** | **Integer** | The ID of the subaccount. | [optional] |
| **country** | **String** | The country code. | [optional] |
| **carrier** | **String** | The carrier information. | [optional] |
| **first_name** | **String** | The first name of the sender. | [optional] |
| **last_name** | **String** | The last name of the sender. | [optional] |
| **_api_username** | **String** | The API username associated with the message. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewMmsHistoryDataAllOfDataInner.new(
  direction: out,
  date: 1436932432,
  to: +16783270696,
  body: Chocolate bar icing icing oat cake carrot cake jelly cotton 1iQByXxdLN.,
  subject: This is a subject,
  priority: 2,
  _media_file_url: https://clicksend-api-downloads.s3.ap-southeast-2.amazonaws.com/_private/example.jpg,
  status: Completed,
  from: sendlist,
  schedule: 1436879372,
  date_added: 1436879372,
  status_code: null,
  status_text: null,
  error_code: null,
  error_text: null,
  message_id: 4E90F4C3-43A3-489D-9AB8-DA1F4332A0C3,
  message_parts: 1.00,
  message_price: 0.070000,
  from_email: null,
  list_id: null,
  custom_string: this is a test,
  contact_id: 0,
  user_id: 1,
  subaccount_id: 1,
  country: US,
  carrier: null,
  first_name: John,
  last_name: Doe,
  _api_username: johndoe
)
```

