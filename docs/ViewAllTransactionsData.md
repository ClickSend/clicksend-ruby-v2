# ClickSend::ViewAllTransactionsData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total** | **Integer** | The total number of items available for viewing. | [optional] |
| **per_page** | **Integer** | The number of items returned per page. This is specified in the limit parameter. You can have 100 items at maximum, and 15 at minimum. | [optional] |
| **current_page** | **Integer** | The current page number. | [optional] |
| **last_page** | **Integer** | The last page number. | [optional] |
| **next_page_url** | **String** | A URL of the next page. It will return **null** if there’s no next page. | [optional] |
| **prev_page_url** | **String** | A URL of the previous page. It will return **null** if there’s no previous page. | [optional] |
| **from** | **Integer** | The number of the first result in the current page. | [optional] |
| **to** | **Integer** | The number of the last result in the current page. | [optional] |
| **data** | [**Array&lt;ViewAllTransactionsDataAllOfDataInner&gt;**](ViewAllTransactionsDataAllOfDataInner.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewAllTransactionsData.new(
  total: 2,
  per_page: 15,
  current_page: 1,
  last_page: 1,
  next_page_url: null,
  prev_page_url: null,
  from: 1,
  to: 2,
  data: [{&quot;invoice_number&quot;:&quot;cb726c65-1c65-47fa-aea2-3ded9ed57557&quot;,&quot;amount&quot;:20,&quot;currency&quot;:&quot;AUD&quot;,&quot;date&quot;:1443420196},{&quot;invoice_number&quot;:&quot;13d35606-5f10-4d31-9de4-065b025aa5b8&quot;,&quot;amount&quot;:20,&quot;currency&quot;:&quot;AUD&quot;,&quot;date&quot;:1443420094}]
)
```

