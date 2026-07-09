# ClickSend::ViewCountries

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP status code of the response. | [optional] |
| **response_code** | **String** | The response code indicating the status of the operation. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | [**Array&lt;Country&gt;**](Country.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewCountries.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: List of Countries.,
  data: [{&quot;code&quot;:&quot;AF&quot;,&quot;value&quot;:&quot;Afghanistan&quot;},{&quot;code&quot;:&quot;AU&quot;,&quot;value&quot;:&quot;Australia&quot;},{&quot;code&quot;:&quot;FI&quot;,&quot;value&quot;:&quot;Finland&quot;}]
)
```

