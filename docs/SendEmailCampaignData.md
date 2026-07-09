# ClickSend::SendEmailCampaignData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **totlal_count** | **Float** | The total count of the email campaigns. | [optional] |
| **total_price** | **String** | The total price of the email campaigns. | [optional] |
| **queued_count** | **Float** | The count of the queued email campaigns. | [optional] |
| **data** | [**EmailCampaign**](EmailCampaign.md) |  | [optional] |
| **_currency** | [**Currency**](Currency.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SendEmailCampaignData.new(
  totlal_count: 1,
  total_price: 0.0066,
  queued_count: 1,
  data: null,
  _currency: null
)
```

