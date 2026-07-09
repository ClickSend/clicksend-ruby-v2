# ClickSend::UpdateSmsInboundAutomationRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dedicated_number** | **String** |  | [optional] |
| **rule_name** | **String** |  | [optional] |
| **message_search_type** | **Integer** |  | [optional] |
| **message_search_term** | **String** |  | [optional] |
| **action** | **String** |  | [optional] |
| **action_address** | **String** |  | [optional] |
| **enabled** | **Integer** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::UpdateSmsInboundAutomationRequest.new(
  dedicated_number: null,
  rule_name: null,
  message_search_type: null,
  message_search_term: null,
  action: null,
  action_address: null,
  enabled: null
)
```

