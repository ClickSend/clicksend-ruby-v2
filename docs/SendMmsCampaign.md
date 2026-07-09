# ClickSend::SendMmsCampaign

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP status code of the response. | [optional] |
| **response_code** | **String** | The response code indicating the status of the operation. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | [**MmsCampaign**](MmsCampaign.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SendMmsCampaign.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: MMS campaign has been created.,
  data: null
)
```

