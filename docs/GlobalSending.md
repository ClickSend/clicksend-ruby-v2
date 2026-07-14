# ClickSend::GlobalSending

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** | The ID of the country. | [optional] |
| **name** | **String** | The name of the country. | [optional] |
| **code** | **String** | The country code. | [optional] |
| **region** | **String** | The region of the country. | [optional] |
| **agreed_at** | **String** | The date when the country was agreed upon. | [optional] |
| **registration_entity** | [**AccountReferrerChosen**](AccountReferrerChosen.md) |  | [optional] |
| **registration_status** | [**GlobalSendingRegistrationStatus**](GlobalSendingRegistrationStatus.md) |  | [optional] |
| **jotform_id** | **String** | The ID of the country in JotForm. | [optional] |
| **sms_registration_type** | **Integer** | The type of SMS registration. | [optional] |
| **block_registration** | **Boolean** | Indicates if registration is blocked. | [optional] |
| **block_leads** | **Boolean** | Indicates if leads are blocked. | [optional] |
| **trial_from_address** | **String** | The trial from address. | [optional] |
| **restricted_sending** | **Boolean** | Indicates if sending is restricted. | [optional] |
| **trial_sending** | **Integer** | Indicates if trial sending is allowed. | [optional] |
| **trial_sending_description** | **String** | Description of trial sending. | [optional] |
| **has_regulation_requirements** | **Integer** | Indicates if there are regulation requirements. | [optional] |
| **registration_steps_url** | **String** | URL for registration steps. | [optional] |
| **regulation_requirements_description** | **String** | Description of regulation requirements. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::GlobalSending.new(
  id: 1,
  name: Australia,
  code: AU,
  region: Oceania,
  agreed_at: null,
  registration_entity: null,
  registration_status: null,
  jotform_id: 12345,
  sms_registration_type: 0,
  block_registration: false,
  block_leads: false,
  trial_from_address: ,
  restricted_sending: false,
  trial_sending: 0,
  trial_sending_description: ,
  has_regulation_requirements: 0,
  registration_steps_url: https://clicksend.helpdocs.com,
  regulation_requirements_description: You can only send from a Dedicated ShortCode. Marketing Messages must be sent from a zero-rated shortcode. Messages must comply with DIA guidelines including opt-in consent and a way to opt-out. https://help.clicksend.com/article/7ifkmw5vd5-australia%22
)
```

