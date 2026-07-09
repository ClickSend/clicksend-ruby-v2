# ClickSend::ViewStrippedStringRulesData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total** | **Integer** | The total number of records in the response. | [optional] |
| **per_page** | **Integer** | The number of records per page. | [optional] |
| **current_page** | **Integer** | The current page number. | [optional] |
| **last_page** | **Integer** | The last page number. | [optional] |
| **next_page_url** | **String** | The URL of the next page of records. | [optional] |
| **prev_page_url** | **String** | The URL of the previous page of records. | [optional] |
| **data** | [**Array&lt;ViewStrippedStringRulesDataDataInner&gt;**](ViewStrippedStringRulesDataDataInner.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewStrippedStringRulesData.new(
  total: 2,
  per_page: 15,
  current_page: 1,
  last_page: 1,
  next_page_url: null,
  prev_page_url: null,
  data: [{&quot;rule_id&quot;:18,&quot;strip_string&quot;:&quot;This is a test1.&quot;},{&quot;rule_id&quot;:19,&quot;strip_string&quot;:&quot;This is a test2.&quot;}]
)
```

