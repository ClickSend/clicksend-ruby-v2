# ClickSend::CalculateEmailCampaignPrice

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP status code of the response. | [optional] |
| **response_code** | **String** | The response code indicating the status of the operation. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | [**CalculateEmailCampaignPriceData**](CalculateEmailCampaignPriceData.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CalculateEmailCampaignPrice.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: Total price for email campaign.,
  data: null
)
```

