# ClickSend::SmsDeliveryReceiptRule

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **receipt_rule_id** | **Integer** | The ID of the receipt rule. | [optional] |
| **rule_name** | **String** | The name of the receipt rule. | [optional] |
| **match_type** | **Integer** | The type of match. | [optional] |
| **action** | **String** | The type of action. | [optional] |
| **action_address** | **String** | The address associated with the action. | [optional] |
| **enabled** | **Integer** | Indicates whether the rule is enabled. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SmsDeliveryReceiptRule.new(
  receipt_rule_id: 5,
  rule_name: My Rule,
  match_type: 0,
  action: EMAIL_FIXED,
  action_address: john@doe.com,
  enabled: 1
)
```

