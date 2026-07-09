# ClickSend::ViewListContacts

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP status code of the response. | [optional] |
| **response_code** | **String** | The response code indicating the status of the operation. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | [**Array&lt;Contact&gt;**](Contact.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewListContacts.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: Here&#39;s your list of contacts.,
  data: [{&quot;contact_id&quot;:552786,&quot;list_id&quot;:428,&quot;phone_number&quot;:&quot;+16783270696&quot;,&quot;first_name&quot;:&quot;Ellen&quot;,&quot;last_name&quot;:&quot;Diaz&quot;,&quot;custom_1&quot;:&quot;&quot;,&quot;custom_2&quot;:&quot;&quot;,&quot;custom_3&quot;:&quot;&quot;,&quot;custom_4&quot;:&quot;&quot;,&quot;date_added&quot;:&quot;1436157486&quot;,&quot;date_updated&quot;:&quot;1436157486&quot;,&quot;fax_number&quot;:null,&quot;organization_name&quot;:null,&quot;email&quot;:null,&quot;address_line_1&quot;:null,&quot;address_line_2&quot;:null,&quot;address_city&quot;:null,&quot;address_state&quot;:null,&quot;address_postal_code&quot;:null,&quot;address_country&quot;:null,&quot;_list_name&quot;:&quot;List6eaG4lGIc9&quot;},{&quot;contact_id&quot;:552787,&quot;list_id&quot;:428,&quot;phone_number&quot;:&quot;+16783270697&quot;,&quot;first_name&quot;:&quot;Ellen&quot;,&quot;last_name&quot;:&quot;Diaz&quot;,&quot;custom_1&quot;:&quot;&quot;,&quot;custom_2&quot;:&quot;&quot;,&quot;custom_3&quot;:&quot;&quot;,&quot;custom_4&quot;:&quot;&quot;,&quot;date_added&quot;:&quot;1436157925&quot;,&quot;date_updated&quot;:&quot;1436157925&quot;,&quot;fax_number&quot;:null,&quot;organization_name&quot;:null,&quot;email&quot;:null,&quot;address_line_1&quot;:null,&quot;address_line_2&quot;:null,&quot;address_city&quot;:null,&quot;address_state&quot;:null,&quot;address_postal_code&quot;:null,&quot;address_country&quot;:null,&quot;_list_name&quot;:&quot;List6eaG4lGIc9&quot;}]
)
```

