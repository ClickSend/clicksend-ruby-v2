# ClickSend::VoiceDeliveryReceiptRule

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **receipt_rule_id** | **Integer** | The ID of the receipt rule. | [optional] |
| **rule_name** | **String** | The name of the receipt rule. | [optional] |
| **match_type** | **Integer** | The match type of the receipt rule. | [optional] |
| **action** | **String** | The action of the receipt rule. | [optional] |
| **action_address** | **String** | The action address of the receipt rule. | [optional] |
| **enabled** | **Integer** | The enabled status of the receipt rule. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::VoiceDeliveryReceiptRule.new(
  receipt_rule_id: 2,
  rule_name: My Rule 2,
  match_type: 3,
  action: URL,
  action_address: http://yourdomain.com,
  enabled: 1
)
```

