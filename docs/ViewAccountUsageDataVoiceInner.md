# ClickSend::ViewAccountUsageDataVoiceInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **subaccount_id** | **Integer** | The subaccount identifier. | [optional] |
| **username** | **String** | The username associated with the subaccount. | [optional] |
| **total_count** | **String** | The total count of voice calls. | [optional] |
| **total_price** | **String** | The total price of voice calls. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewAccountUsageDataVoiceInner.new(
  subaccount_id: null,
  username: null,
  total_count: null,
  total_price: null
)
```

