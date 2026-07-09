# ClickSend::ViewAvailableNumbers

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP status code of the response. | [optional] |
| **response_code** | **String** | The response code indicating the status of the operation. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | [**Array&lt;ViewAvailableNumbersDataInner&gt;**](ViewAvailableNumbersDataInner.md) |  | [optional] |
| **_currency** | [**Currency**](Currency.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewAvailableNumbers.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: Here are some numbers.,
  data: [{&quot;country&quot;:&quot;AU&quot;,&quot;country_name&quot;:&quot;Australia&quot;,&quot;dedicated_number&quot;:&quot;+61280662298&quot;,&quot;price_setup&quot;:&quot;0.0000&quot;,&quot;price_monthly&quot;:&quot;20.7100&quot;,&quot;price_total&quot;:&quot;20.7100&quot;,&quot;address_requirement&quot;:&quot;local&quot;},{&quot;country&quot;:&quot;AU&quot;,&quot;country_name&quot;:&quot;Australia&quot;,&quot;dedicated_number&quot;:&quot;+61280662299&quot;,&quot;price_setup&quot;:&quot;0.0000&quot;,&quot;price_monthly&quot;:&quot;20.7100&quot;,&quot;price_total&quot;:&quot;20.7100&quot;,&quot;address_requirement&quot;:&quot;local&quot;}],
  _currency: null
)
```

