# ClickSend::ViewMasterEmailTemplates

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP status code of the response. | [optional] |
| **response_code** | **String** | The response code indicating the status of the operation. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | [**Array&lt;MasterEmailTemplate&gt;**](MasterEmailTemplate.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewMasterEmailTemplates.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: List of Email Master Templates,
  data: [{&quot;template_id_master&quot;:57,&quot;template_name&quot;:&quot;Welcome Email&quot;,&quot;date_added&quot;:&quot;1436157486&quot;,&quot;thumbnail&quot;:{&quot;small&quot;:&quot;https://s3-ap-southeast-2.amazonaws.com/clicksend-api-downloads/_email-marketing/_templates-master/basic2/thumb-small.jpg&quot;,&quot;large&quot;:&quot;https://s3-ap-southeast-2.amazonaws.com/clicksend-api-downloads/_email-marketing/_templates-master/basic2/thumb-large.jpg&quot;}},{&quot;template_id_master&quot;:1,&quot;template_name&quot;:&quot;Minty&quot;,&quot;date_added&quot;:&quot;1445848821&quot;,&quot;thumbnail&quot;:{&quot;small&quot;:&quot;https://s3-ap-southeast-2.amazonaws.com/clicksend-api-downloads/_email-marketing/_templates-master/minty/thumb-small.jpg&quot;,&quot;large&quot;:&quot;https://s3-ap-southeast-2.amazonaws.com/clicksend-api-downloads/_email-marketing/_templates-master/minty/thumb-large.jpg&quot;}}]
)
```

