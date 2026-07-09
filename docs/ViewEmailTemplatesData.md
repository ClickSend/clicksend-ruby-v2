# ClickSend::ViewEmailTemplatesData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total** | **Integer** | The total number of records in the response. | [optional] |
| **per_page** | **Integer** | The number of records per page. | [optional] |
| **current_page** | **Integer** | The current page number. | [optional] |
| **last_page** | **Integer** | The last page number. | [optional] |
| **next_page_url** | **String** | The URL of the next page of records. | [optional] |
| **prev_page_url** | **String** | The URL of the previous page of records. | [optional] |
| **from** | **Integer** | The index of the first record in the page. | [optional] |
| **to** | **Integer** | The index of the last record in the page. | [optional] |
| **data** | [**Array&lt;ViewEmailTemplatesDataDataInner&gt;**](ViewEmailTemplatesDataDataInner.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewEmailTemplatesData.new(
  total: 2,
  per_page: 15,
  current_page: 1,
  last_page: 1,
  next_page_url: null,
  prev_page_url: null,
  from: 1,
  to: 15,
  data: [{&quot;template_id&quot;:281,&quot;template_name&quot;:&quot;Test&quot;},{&quot;template_id&quot;:290,&quot;template_name&quot;:&quot;Minions&quot;}]
)
```

