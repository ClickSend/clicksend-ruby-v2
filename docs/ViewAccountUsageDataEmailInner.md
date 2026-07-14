# ClickSend::ViewAccountUsageDataEmailInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **subaccount_id** | **Integer** | The subaccount identifier. | [optional] |
| **username** | **String** | The username associated with the subaccount. | [optional] |
| **total_count** | **Integer** | The total count of emails. | [optional] |
| **total_price** | **String** |  | [optional] |
| **notes** | **String** | Optional notes. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewAccountUsageDataEmailInner.new(
  subaccount_id: null,
  username: null,
  total_count: null,
  total_price: null,
  notes: null
)
```

