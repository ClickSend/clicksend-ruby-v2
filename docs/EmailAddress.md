# ClickSend::EmailAddress

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email_address_id** | **Integer** | The unique identifier for the email address. | [optional] |
| **email_address** | **String** | The email address. | [optional] |
| **verified** | **Integer** | Flag indicating if the email address is verified. | [optional] |
| **date_added** | **String** | The date the email address was added. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::EmailAddress.new(
  email_address_id: 2,
  email_address: test2@user.com,
  verified: 0,
  date_added: 1436157486
)
```

