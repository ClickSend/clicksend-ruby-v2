# ClickSend::SmsTemplate

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **template_id** | **Integer** | The generated ID of the template. | [optional] |
| **body** | **String** | The main content of the template. | [optional] |
| **template_name** | **String** | The name of the template. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SmsTemplate.new(
  template_id: 1,
  body: This is a sample template.,
  template_name: My Awesome Template
)
```

