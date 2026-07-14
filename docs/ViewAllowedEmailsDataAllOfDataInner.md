# ClickSend::ViewAllowedEmailsDataAllOfDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email_address_id** | **Float** | The ID of the email address. | [optional] |
| **email_address** | **String** | The email address. | [optional] |
| **from** | **String** | The sender. | [optional] |
| **subaccount_id** | **Integer** | The ID of the subaccount that owns this email address. | [optional] |
| **from_fax** | **String** | The fax number used as the sender, if applicable. | [optional] |
| **voice** | **String** | The voice used when this email address triggers a voice message. | [optional] |
| **lang** | **String** | The language used when this email address triggers a voice message. | [optional] |
| **_subaccount_name** | **String** | The name of the subaccount that owns this email address. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewAllowedEmailsDataAllOfDataInner.new(
  email_address_id: 1,
  email_address: my@email.com,
  from: +13523944199,
  subaccount_id: 345789,
  from_fax: ,
  voice: male,
  lang: en-us,
  _subaccount_name: my@email.com
)
```

