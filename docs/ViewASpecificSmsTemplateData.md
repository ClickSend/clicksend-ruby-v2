# ClickSend::ViewASpecificSmsTemplateData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **template_id** | **Integer** | The generated ID of the template. | [optional] |
| **template_name** | **String** | The main content of the template. | [optional] |
| **body** | **String** | The name of the template. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewASpecificSmsTemplateData.new(
  template_id: 1,
  template_name: Template 501916,
  body: This is a test template.
new line 漢字 here.
)
```

