# ClickSend::ViewTemplateCategories

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP status code of the response. | [optional] |
| **response_code** | **String** | The response code indicating the status of the operation. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | [**Array&lt;ViewTemplateCategoriesDataInner&gt;**](ViewTemplateCategoriesDataInner.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewTemplateCategories.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: List of Email Categories,
  data: [{&quot;category_id&quot;:2,&quot;category_name&quot;:&quot;Alerts/Notificartions&quot;},{&quot;category_id&quot;:3,&quot;category_name&quot;:&quot;Art&quot;},{&quot;category_id&quot;:4,&quot;category_name&quot;:&quot;Birthday&quot;},{&quot;category_id&quot;:23,&quot;category_name&quot;:&quot;Blank Template&quot;}]
)
```

