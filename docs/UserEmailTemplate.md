# ClickSend::UserEmailTemplate

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **template_id** | **Integer** | The unique identifier for the template. | [optional] |
| **template_id_master** | **Integer** | The unique identifier for the template. | [optional] |
| **template_name** | **String** | The name of the template. | [optional] |
| **body** | **String** | The body of the template. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::UserEmailTemplate.new(
  template_id: 292,
  template_id_master: 57,
  template_name: new minion template!,
  body: &lt;div id&#x3D;&quot;nb_wrapper&quot;&gt;&lt;!DOCTYPE html PUBLIC &quot;-//W3C//DTD XHTML 1.0 Transitional//EN&quot;...
)
```

