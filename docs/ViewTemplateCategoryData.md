# ClickSend::ViewTemplateCategoryData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **category_id** | **Float** | The ID of the category. | [optional] |
| **name** | **String** | The name of the category. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewTemplateCategoryData.new(
  category_id: 4,
  name: Birthday
)
```

