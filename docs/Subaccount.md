# ClickSend::Subaccount

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **subaccount_id** | **Integer** | The unique identifier for the subaccount. | [optional] |
| **api_username** | **String** | The API username of the subaccount. | [optional] |
| **email** | **String** | The email address of the subaccount. | [optional] |
| **phone_number** | **String** | The phone number of the subaccount. | [optional] |
| **first_name** | **String** | The first name of the subaccount. | [optional] |
| **last_name** | **String** | The last name of the subaccount. | [optional] |
| **api_key** | **String** | The API key of the subaccount. | [optional] |
| **access_smpp** | **Integer** | Flag indicating if the subaccount has access to SMPP. | [optional] |
| **access_users** | **Integer** | Flag indicating if the subaccount has access to users. | [optional] |
| **access_billing** | **Integer** | Flag indicating if the subaccount has access to billing. | [optional] |
| **access_reporting** | **Integer** | Flag indicating if the subaccount has access to reporting. | [optional] |
| **access_contacts** | **Integer** | Flag indicating if the subaccount has access to contacts. | [optional] |
| **access_settings** | **Integer** | Flag indicating if the subaccount has access to settings. | [optional] |
| **access_sms** | **Integer** | Flag indicating if the subaccount has access to SMS. | [optional] |
| **access_email** | **Integer** | Flag indicating if the subaccount has access to email. | [optional] |
| **access_voice** | **Integer** | Flag indicating if the subaccount has access to voice services. | [optional] |
| **access_fax** | **Integer** | Flag indicating if the subaccount has access to fax services. | [optional] |
| **access_post** | **Integer** | Flag indicating if the subaccount has access to post services. | [optional] |
| **access_reseller** | **Integer** | Flag indicating if the subaccount has access to reseller services. | [optional] |
| **access_global_sending** | **Integer** | Flag indicating if the subaccount has access to global sending. | [optional] |
| **access_mms** | **Integer** | Flag indicating if the subaccount has access to MMS services. | [optional] |
| **hide_pricing** | **Integer** | Flag indicating if pricing is hidden for the subaccount. | [optional] |
| **share_campaigns** | **Integer** | Flag indicating if the subaccount can share campaigns. | [optional] |
| **notes** | **String** | Additional notes for the subaccount. | [optional] |
| **is_main** | **Integer** | Flag indicating if this is the main account rather than a subaccount. | [optional] |
| **sign_up_type** | **String** | The sign-up type used to create the subaccount, if applicable. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::Subaccount.new(
  subaccount_id: 126,
  api_username: johndoe1,
  email: johndoe1@awesome.com,
  phone_number: +15184811001,
  first_name: John,
  last_name: Doe,
  api_key: F3702045-EB2C-0091-C211-7728048DCAE2,
  access_smpp: 0,
  access_users: 1,
  access_billing: 1,
  access_reporting: 1,
  access_contacts: 1,
  access_settings: 1,
  access_sms: 1,
  access_email: 1,
  access_voice: 1,
  access_fax: 1,
  access_post: 1,
  access_reseller: 1,
  access_global_sending: 1,
  access_mms: 1,
  hide_pricing: 0,
  share_campaigns: 0,
  notes: null,
  is_main: 0,
  sign_up_type: null
)
```

