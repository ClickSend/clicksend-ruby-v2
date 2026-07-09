# ClickSend::CreateFaxDeliveryReceiptRuleRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **rule_name** | **String** |  | [optional] |
| **match_type** | **Integer** |  | [optional] |
| **action** | **String** |  | [optional] |
| **action_address** | **String** |  | [optional] |
| **enabled** | **Integer** |  | [optional] |
| **url** | **String** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CreateFaxDeliveryReceiptRuleRequest.new(
  rule_name: null,
  match_type: null,
  action: null,
  action_address: null,
  enabled: null,
  url: null
)
```

