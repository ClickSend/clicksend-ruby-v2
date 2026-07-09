# ClickSend::SmsTemplateUpdate

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **template_id** | **Integer** | The generated ID of the template. This remains the same and can’t be updated. | [optional] |
| **body** | **String** | The new updated content of the template. | [optional] |
| **template_name** | **String** | The new updated name of the template. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SmsTemplateUpdate.new(
  template_id: 1,
  body: This is a sample template.,
  template_name: My Awesome Template
)
```

