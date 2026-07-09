# ClickSend::CreateDeliveryIssueRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** |  | [optional] |
| **type** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **email_address** | **String** |  | [optional] |
| **client_comments** | **String** |  | [optional] |
| **support_comments** | **String** |  | [optional] |
| **resolved** | **Boolean** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CreateDeliveryIssueRequest.new(
  message_id: null,
  type: null,
  description: null,
  email_address: null,
  client_comments: null,
  support_comments: null,
  resolved: null
)
```

