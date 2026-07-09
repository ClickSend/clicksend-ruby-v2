# ClickSend::CalculateMmsCampaignPriceDataData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **from** | **String** | The sender id. | [optional] |
| **schedule** | **String** | The schedule timestamp. | [optional] |
| **body** | **String** | The message body. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CalculateMmsCampaignPriceDataData.new(
  from: +61411111111,
  schedule: 1577833200,
  body: Hey test, I want to ask if this is your lastname: ? Also, do you like koalas?
)
```

