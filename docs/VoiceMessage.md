# ClickSend::VoiceMessage

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **date** | **Float** | The date. | [optional] |
| **to** | **String** | The recipient&#39;s phone number. | [optional] |
| **to_type** | **String** | The type of recipient. | [optional] |
| **body** | **String** | The body of the message. | [optional] |
| **from** | **String** | The sender&#39;s phone number. | [optional] |
| **lang** | **String** | The language of the message. | [optional] |
| **voice** | **String** | The voice of the message. | [optional] |
| **schedule** | **Integer** | The timestamp when the message should be sent. | [optional] |
| **message_id** | **String** | The ID of the message. | [optional] |
| **message_parts** | **Integer** | The number of parts in the message. | [optional] |
| **message_price** | **String** | The price of the message. | [optional] |
| **custom_string** | **String** | The custom string of the message. | [optional] |
| **user_id** | **Float** | The ID of the user. | [optional] |
| **subaccount_id** | **Float** | The ID of the subaccount. | [optional] |
| **country** | **String** | The country code of the message. | [optional] |
| **require_input** | **Float** | The require input of the message. | [optional] |
| **machine_detection** | **Float** | The machine detection of the message. | [optional] |
| **status** | **String** | The status of the message. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::VoiceMessage.new(
  date: 1436871253,
  to: +61411111111,
  to_type: mobile,
  body: Jelly liquorice marshmallow candy carrot cake 4Eyffjs1vL.,
  from: null,
  lang: en-au,
  voice: female,
  schedule: 1436874701,
  message_id: BF7AD270-0DE2-418B-B606-71D527D9C1AE,
  message_parts: 1,
  message_price: 0.07,
  custom_string: this is a test,
  user_id: 1,
  subaccount_id: 1,
  country: AU,
  require_input: 0,
  machine_detection: 0,
  status: SUCCESS
)
```

