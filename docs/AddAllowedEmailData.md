# ClickSend::AddAllowedEmailData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email_address_id** | **Float** | The ID of the email address. | [optional] |
| **email_address** | **String** | The email address. | [optional] |
| **from** | **String** | The sender. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::AddAllowedEmailData.new(
  email_address_id: 107,
  email_address: Cv3p0@gmail.com,
  from: +17128845887
)
```

