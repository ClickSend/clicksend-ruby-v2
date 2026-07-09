# ClickSend::FaxDeliveryReceiptRule

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **receipt_rule_id** | **Integer** | The ID of the receipt rule. | [optional] |
| **rule_name** | **String** | The name of the receipt rule. | [optional] |
| **match_type** | **Integer** | The type of match. | [optional] |
| **action** | **String** | The action triggered by the rule. | [optional] |
| **action_address** | **String** | The address associated with the action. | [optional] |
| **enabled** | **Integer** | Indicates whether the rule is enabled. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::FaxDeliveryReceiptRule.new(
  receipt_rule_id: 1,
  rule_name: Email Test Rule,
  match_type: 0,
  action: URL,
  action_address: http://yourdomain.com,
  enabled: 1
)
```

