# ClickSend::AddAllowedEmailRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email_address** | **String** |  | [optional] |
| **from** | **String** |  | [optional] |
| **from_fax** | **String** |  | [optional] |
| **subaccount_id** | **String** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::AddAllowedEmailRequest.new(
  email_address: null,
  from: null,
  from_fax: null,
  subaccount_id: null
)
```

