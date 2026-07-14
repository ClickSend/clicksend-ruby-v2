# ClickSend::ViewAllowedEmailsData

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
| **data** | [**Array&lt;ViewAllowedEmailsDataAllOfDataInner&gt;**](ViewAllowedEmailsDataAllOfDataInner.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewAllowedEmailsData.new(
  total: 2,
  per_page: 15,
  current_page: 1,
  last_page: 1,
  next_page_url: null,
  prev_page_url: null,
  from: 1,
  to: 2,
  data: [{&quot;email_address_id&quot;:84,&quot;email_address&quot;:&quot;my@email.com&quot;,&quot;from&quot;:&quot;+13523944199&quot;,&quot;subaccount_id&quot;:345789,&quot;from_fax&quot;:&quot;&quot;,&quot;voice&quot;:&quot;male&quot;,&quot;lang&quot;:&quot;en-us&quot;,&quot;_subaccount_name&quot;:&quot;my@email.com&quot;},{&quot;email_address_id&quot;:85,&quot;email_address&quot;:&quot;my@email.com&quot;,&quot;from&quot;:&quot;+13523944199&quot;,&quot;subaccount_id&quot;:345789,&quot;from_fax&quot;:&quot;&quot;,&quot;voice&quot;:&quot;male&quot;,&quot;lang&quot;:&quot;en-us&quot;,&quot;_subaccount_name&quot;:&quot;my@email.com&quot;}]
)
```

