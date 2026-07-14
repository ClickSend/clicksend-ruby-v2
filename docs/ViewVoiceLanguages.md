# ClickSend::ViewVoiceLanguages

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP status code of the response. | [optional] |
| **response_code** | **String** | The response code indicating the status of the operation. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | [**Array&lt;ViewVoiceLanguagesDataInner&gt;**](ViewVoiceLanguagesDataInner.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewVoiceLanguages.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: Here are the possible languages.,
  data: [{&quot;code&quot;:&quot;en-us&quot;,&quot;country&quot;:&quot;English, US&quot;,&quot;gender&quot;:&quot;male&quot;},{&quot;code&quot;:&quot;en-au&quot;,&quot;country&quot;:&quot;English, Australia&quot;,&quot;gender&quot;:[&quot;female&quot;,&quot;male&quot;]}]
)
```

