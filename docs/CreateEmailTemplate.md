# ClickSend::CreateEmailTemplate

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP status code of the response. | [optional] |
| **response_code** | **String** | The response code indicating the status of the operation. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | [**UserEmailTemplate**](UserEmailTemplate.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CreateEmailTemplate.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: New email template has been saved.,
  data: null
)
```

