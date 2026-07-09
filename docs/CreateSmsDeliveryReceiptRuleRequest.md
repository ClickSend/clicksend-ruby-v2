# ClickSend::CreateSmsDeliveryReceiptRuleRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **rule_name** | **String** |  | [optional] |
| **match_type** | **Integer** |  | [optional] |
| **action** | **String** |  | [optional] |
| **action_address** | **String** |  | [optional] |
| **enabled** | **Integer** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CreateSmsDeliveryReceiptRuleRequest.new(
  rule_name: null,
  match_type: null,
  action: null,
  action_address: null,
  enabled: null
)
```

