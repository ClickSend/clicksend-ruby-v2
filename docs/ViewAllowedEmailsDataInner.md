# ClickSend::ViewAllowedEmailsDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email_address_id** | **Float** | The ID of the email address. | [optional] |
| **email_address** | **String** | The email address. | [optional] |
| **from** | **String** | The sender. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewAllowedEmailsDataInner.new(
  email_address_id: 1,
  email_address: my@email.com,
  from: +13523944199
)
```

