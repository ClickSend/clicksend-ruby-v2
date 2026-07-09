# ClickSend::ViewReferralAccountsDataAllOfDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **referral_rule_id** | **Integer** | The ID of the Referral Account. | [optional] |
| **refered_user_id** | **Integer** | The ID of the Referral Account. | [optional] |
| **date_referred** | **Float** | The ID of the Referral Account. | [optional] |
| **percentage_referral** | **Float** | The Percentage of the Referral. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewReferralAccountsDataAllOfDataInner.new(
  referral_rule_id: null,
  refered_user_id: null,
  date_referred: 1438260940,
  percentage_referral: 5
)
```

