# ClickSend::ViewAvailableNumbersData

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
| **data** | [**Array&lt;ViewAvailableNumbersDataAllOfDataInner&gt;**](ViewAvailableNumbersDataAllOfDataInner.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewAvailableNumbersData.new(
  total: 2,
  per_page: 15,
  current_page: 1,
  last_page: 1,
  next_page_url: null,
  prev_page_url: null,
  from: 1,
  to: 2,
  data: [{&quot;country&quot;:&quot;AU&quot;,&quot;country_name&quot;:&quot;Australia&quot;,&quot;dedicated_number&quot;:&quot;+61280662298&quot;,&quot;price_setup&quot;:&quot;0.0000&quot;,&quot;price_monthly&quot;:&quot;20.7100&quot;,&quot;price_total&quot;:&quot;20.7100&quot;,&quot;address_requirement&quot;:&quot;local&quot;},{&quot;country&quot;:&quot;AU&quot;,&quot;country_name&quot;:&quot;Australia&quot;,&quot;dedicated_number&quot;:&quot;+61280662299&quot;,&quot;price_setup&quot;:&quot;0.0000&quot;,&quot;price_monthly&quot;:&quot;20.7100&quot;,&quot;price_total&quot;:&quot;20.7100&quot;,&quot;address_requirement&quot;:&quot;local&quot;}]
)
```

