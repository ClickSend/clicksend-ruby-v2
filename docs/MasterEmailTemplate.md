# ClickSend::MasterEmailTemplate

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **template_id_master** | **Integer** | The unique identifier for the template. | [optional] |
| **template_name** | **String** | The name of the template. | [optional] |
| **date_added** | **Integer** | The date the template was added. | [optional] |
| **body** | **String** | The body of the template. | [optional] |
| **thumbnail** | [**MasterEmailTemplateThumbnail**](MasterEmailTemplateThumbnail.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::MasterEmailTemplate.new(
  template_id_master: 57,
  template_name: Welcome Email,
  date_added: 1436157486,
  body: &lt;!DOCTYPE html PUBLIC &quot;-//W3C//DTD XHTML 1.0 Transitional//EN&quot; ...
                     &lt;/tr&gt;
                  &lt;/tbody&gt;
               &lt;/table&gt;
            &lt;/td&gt;
         &lt;/tr&gt;
      &lt;/tbody&gt;
   &lt;/table&gt;
&lt;/body&gt;
&lt;/html&gt;,
  thumbnail: null
)
```

