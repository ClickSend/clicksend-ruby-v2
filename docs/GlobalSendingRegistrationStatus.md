# ClickSend::GlobalSendingRegistrationStatus

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** | The ID of the registration status. | [optional] |
| **name** | **String** | The name of the registration status. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::GlobalSendingRegistrationStatus.new(
  id: 1,
  name: NOT_INITIATED
)
```

