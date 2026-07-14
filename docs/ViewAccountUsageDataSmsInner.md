# ClickSend::ViewAccountUsageDataSmsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **subaccount_id** | **Integer** | The subaccount identifier. | [optional] |
| **username** | **String** | The username associated with the subaccount. | [optional] |
| **total_count** | **String** | The total count of SMS. | [optional] |
| **total_price** | **Float** | The total price of SMS. | [optional] |
| **notes** | **String** | Optional notes. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewAccountUsageDataSmsInner.new(
  subaccount_id: null,
  username: null,
  total_count: null,
  total_price: null,
  notes: null
)
```

