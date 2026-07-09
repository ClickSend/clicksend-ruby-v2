# ClickSend::InboundFaxRule

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **inbound_rule_id** | **Integer** | The ID of the inbound rule | [optional] |
| **dedicated_number** | **String** | The dedicated number | [optional] |
| **rule_name** | **String** | The name of the inbound rule | [optional] |
| **user_id** | **Integer** | The ID of the user | [optional] |
| **action** | **String** | The action | [optional] |
| **action_address** | **String** | The address associated with the action | [optional] |
| **enabled** | **Integer** | Indicates whether the rule is enabled | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::InboundFaxRule.new(
  inbound_rule_id: 1,
  dedicated_number: 19,
  rule_name: Email,
  user_id: 1,
  action: EMAIL_FIXED,
  action_address: test@test.com,
  enabled: 1
)
```

