# ClickSend::VoiceMessage

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **date** | **String** | The date, if applicable. May be null; see also &#x60;date_added&#x60;. | [optional] |
| **date_added** | **Integer** | The Unix timestamp when the message was added. | [optional] |
| **list_id** | **String** | The ID of the list associated with the message, if applicable. | [optional] |
| **to** | **String** | The recipient&#39;s phone number. | [optional] |
| **to_type** | **String** | The type of recipient. | [optional] |
| **body** | **String** | The body of the message. | [optional] |
| **from** | **String** | The sender&#39;s phone number. | [optional] |
| **lang** | **String** | The language of the message. | [optional] |
| **voice** | **String** | The voice of the message. | [optional] |
| **schedule** | [**VoiceMessageSchedule**](VoiceMessageSchedule.md) |  | [optional] |
| **message_id** | **String** | The ID of the message. | [optional] |
| **message_parts** | **Integer** | The number of parts in the message. | [optional] |
| **message_price** | **String** | The price of the message. | [optional] |
| **custom_string** | **String** | The custom string of the message. | [optional] |
| **user_id** | **Float** | The ID of the user. | [optional] |
| **subaccount_id** | **Float** | The ID of the subaccount. | [optional] |
| **country** | **String** | The country code of the message. | [optional] |
| **require_input** | **Float** | The require input of the message. | [optional] |
| **machine_detection** | **Float** | The machine detection of the message. | [optional] |
| **machine_detected** | **Float** | Flag indicating if an answering machine was detected. | [optional] |
| **digits** | **String** | The digits entered by the recipient, if any input was collected. | [optional] |
| **carrier** | **String** | The carrier of the recipient&#39;s phone number. | [optional] |
| **status_code** | **String** | The status code of the message. | [optional] |
| **status_text** | **String** | A human-readable description of the status. | [optional] |
| **status** | **String** | The status of the message. | [optional] |
| **_api_username** | **String** | The API username associated with the message. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::VoiceMessage.new(
  date: 1436871253,
  date_added: 1436871253,
  list_id: null,
  to: +61411111111,
  to_type: mobile,
  body: Jelly liquorice marshmallow candy carrot cake 4Eyffjs1vL.,
  from: null,
  lang: en-au,
  voice: female,
  schedule: null,
  message_id: BF7AD270-0DE2-418B-B606-71D527D9C1AE,
  message_parts: 1,
  message_price: 0.07,
  custom_string: this is a test,
  user_id: 1,
  subaccount_id: 1,
  country: AU,
  require_input: 0,
  machine_detection: 0,
  machine_detected: 0,
  digits: null,
  carrier: Telstra,
  status_code: 201,
  status_text: Delivered,
  status: SUCCESS,
  _api_username: johndoe1
)
```

