# ClickSend::ViewReferralAccountsData

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
| **data** | [**Array&lt;ViewReferralAccountsDataAllOfDataInner&gt;**](ViewReferralAccountsDataAllOfDataInner.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewReferralAccountsData.new(
  total: 2,
  per_page: 15,
  current_page: 1,
  last_page: 1,
  next_page_url: null,
  prev_page_url: null,
  from: 1,
  to: 2,
  data: [{&quot;referral_rule_id&quot;:1,&quot;refered_user_id&quot;:24,&quot;date_referred&quot;:1438260940,&quot;percentage_referral&quot;:5},{&quot;referral_rule_id&quot;:2,&quot;refered_user_id&quot;:25,&quot;date_referred&quot;:1438260989,&quot;percentage_referral&quot;:5}]
)
```

