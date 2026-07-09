# ClickSend::DefaultSenderError

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | HTTP status code of the response. |  |
| **response_code** | **String** | Code indicating the result of the response. |  |
| **response_msg** | **String** | Message providing additional information. |  |
| **data** | **Object** |  | [optional] |
| **details** | [**Array&lt;DefaultSenderErrorDetailsInner&gt;**](DefaultSenderErrorDetailsInner.md) | List of error details |  |

## Example

```ruby
require 'clicksend'

instance = ClickSend::DefaultSenderError.new(
  http_code: 400,
  response_code: BAD_REQUEST,
  response_msg: Failed to process default sender,
  data: null,
  details: [{&quot;field&quot;:&quot;default_sender_strategies[0].sender_id&quot;,&quot;reason&quot;:&quot;Invalid sender ID format&quot;},{&quot;field&quot;:&quot;default_sender_strategies[0].sender_type&quot;,&quot;reason&quot;:&quot;Sender type is required&quot;}]
)
```

