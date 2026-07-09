# ClickSend::ViewStrippedStringRuleData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **rule_id** | **Integer** | The rule id | [optional] |
| **stripped_string** | **String** | The string to be stripped | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewStrippedStringRuleData.new(
  rule_id: 18,
  stripped_string: You&#39;ve received a reply from.
)
```

