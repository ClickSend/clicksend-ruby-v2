# ClickSend::CreateSmsTemplateRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **template_name** | **String** | The name of the template. | [optional] |
| **body** | **String** | body String The main content of your template. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CreateSmsTemplateRequest.new(
  template_name: Template 501916,
  body: null
)
```

