# ClickSend::SmsInboundRule

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **inbound_rule_id** | **Integer** | The ID of the inbound rule. | [optional] |
| **dedicated_number** | **String** | The number to be used in the inbound rule. | [optional] |
| **rule_name** | **String** | The name of the inbound rule. | [optional] |
| **message_search_type** | **Integer** | The type of message search to be used in the inbound rule. | [optional] |
| **message_search_term** | **String** | The message search term to be used in the inbound rule. | [optional] |
| **action** | **String** | The action to be taken in the inbound rule. | [optional] |
| **action_address** | **String** | The action address to be used in the inbound rule. | [optional] |
| **body** | **String** | The body of the inbound rule. | [optional] |
| **enabled** | **Integer** | The status of the inbound rule. | [optional] |
| **webhook_type** | **String** | The format used when calling the webhook (e.g. post, json). | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SmsInboundRule.new(
  inbound_rule_id: 10,
  dedicated_number: +61298441484,
  rule_name: My Rule 10,
  message_search_type: 3,
  message_search_term: My Search Term,
  action: CREATE_CONTACT_PLUS_EMAIL,
  action_address: 430,
  body: Hello, World!,
  enabled: 1,
  webhook_type: json
)
```

