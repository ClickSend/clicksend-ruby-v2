# ClickSend::ViewAllowedEmails

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP status code of the response. | [optional] |
| **response_code** | **String** | The response code indicating the status of the operation. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | [**Array&lt;ViewAllowedEmailsDataInner&gt;**](ViewAllowedEmailsDataInner.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewAllowedEmails.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: Here are some data.,
  data: [{&quot;email_address_id&quot;:84,&quot;email_address&quot;:&quot;my@email.com&quot;,&quot;from&quot;:&quot;+13523944199&quot;},{&quot;email_address_id&quot;:85,&quot;email_address&quot;:&quot;my@email.com&quot;,&quot;from&quot;:&quot;+13523944199&quot;}]
)
```

