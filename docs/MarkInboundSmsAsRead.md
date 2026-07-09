# ClickSend::MarkInboundSmsAsRead

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP code of the response. Visit [this page](/#status-codes) for more information. | [optional] |
| **response_code** | **String** | The response code of the operation. Visit [this page](/#status-codes) for more information. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | **Object** | The parameters related to the inbound SMS.  &lt;div class&#x3D;\&quot;warning-box\&quot;&gt;   &lt;h4&gt;&lt;i class&#x3D;\&quot;fas fa-exclamation-triangle\&quot;&gt;&lt;/i&gt; Warning:&lt;/h4&gt;   &lt;p&gt;This parameter is deprecated and will return &lt;strong&gt;null&lt;/strong/&gt;.&lt;/p&gt; &lt;/div&gt; | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::MarkInboundSmsAsRead.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: Inbound messages have been marked as read.,
  data: null
)
```

