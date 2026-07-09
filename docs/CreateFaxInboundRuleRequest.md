# ClickSend::CreateFaxInboundRuleRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dedicated_number** | **String** |  | [optional] |
| **rule_name** | **String** |  | [optional] |
| **action** | **String** |  | [optional] |
| **action_address** | **String** |  | [optional] |
| **enabled** | **Integer** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CreateFaxInboundRuleRequest.new(
  dedicated_number: null,
  rule_name: null,
  action: null,
  action_address: null,
  enabled: null
)
```

