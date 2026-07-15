# ClickSend::ViewAccountUsageData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **sms** | [**Array&lt;ViewAccountUsageDataSmsInner&gt;**](ViewAccountUsageDataSmsInner.md) |  | [optional] |
| **mms** | [**Array&lt;ViewAccountUsageDataSmsInner&gt;**](ViewAccountUsageDataSmsInner.md) |  | [optional] |
| **voice** | [**Array&lt;ViewAccountUsageDataSmsInner&gt;**](ViewAccountUsageDataSmsInner.md) |  | [optional] |
| **fax** | [**Array&lt;ViewAccountUsageDataSmsInner&gt;**](ViewAccountUsageDataSmsInner.md) |  | [optional] |
| **post** | [**Array&lt;ViewAccountUsageDataSmsInner&gt;**](ViewAccountUsageDataSmsInner.md) |  | [optional] |
| **email** | [**Array&lt;ViewAccountUsageDataEmailInner&gt;**](ViewAccountUsageDataEmailInner.md) |  | [optional] |
| **email_transactional** | [**Array&lt;ViewAccountUsageDataEmailInner&gt;**](ViewAccountUsageDataEmailInner.md) |  | [optional] |
| **postcards** | [**Array&lt;ViewAccountUsageDataSmsInner&gt;**](ViewAccountUsageDataSmsInner.md) |  | [optional] |
| **sms_total** | [**ViewVoiceStatisticsDataTotalOutbound**](ViewVoiceStatisticsDataTotalOutbound.md) |  | [optional] |
| **voice_total** | [**ViewVoiceStatisticsDataTotalOutbound**](ViewVoiceStatisticsDataTotalOutbound.md) |  | [optional] |
| **fax_total** | [**ViewVoiceStatisticsDataTotalOutbound**](ViewVoiceStatisticsDataTotalOutbound.md) |  | [optional] |
| **post_total** | [**ViewVoiceStatisticsDataTotalOutbound**](ViewVoiceStatisticsDataTotalOutbound.md) |  | [optional] |
| **email_total** | [**ViewVoiceStatisticsDataTotalOutbound**](ViewVoiceStatisticsDataTotalOutbound.md) |  | [optional] |
| **mms_total** | [**ViewVoiceStatisticsDataTotalOutbound**](ViewVoiceStatisticsDataTotalOutbound.md) |  | [optional] |
| **email_transactional_total** | [**ViewVoiceStatisticsDataTotalOutbound**](ViewVoiceStatisticsDataTotalOutbound.md) |  | [optional] |
| **postcards_total** | [**ViewVoiceStatisticsDataTotalOutbound**](ViewVoiceStatisticsDataTotalOutbound.md) |  | [optional] |
| **_currency** | [**Currency**](Currency.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewAccountUsageData.new(
  sms: [{&quot;subaccount_id&quot;:1039,&quot;username&quot;:&quot;gerald&quot;,&quot;total_count&quot;:&quot;29.00&quot;,&quot;total_price&quot;:2.1337},{&quot;subaccount_id&quot;:1047,&quot;username&quot;:&quot;user5&quot;,&quot;total_count&quot;:&quot;4.00&quot;,&quot;total_price&quot;:0.308}],
  mms: [],
  voice: [{&quot;subaccount_id&quot;:1039,&quot;username&quot;:&quot;user1&quot;,&quot;total_count&quot;:&quot;6.00&quot;,&quot;total_price&quot;:0.198},{&quot;subaccount_id&quot;:1047,&quot;username&quot;:&quot;user5&quot;,&quot;total_count&quot;:&quot;1.00&quot;,&quot;total_price&quot;:0.033}],
  fax: [{&quot;subaccount_id&quot;:1039,&quot;username&quot;:&quot;user1&quot;,&quot;total_count&quot;:&quot;3.00&quot;,&quot;total_price&quot;:0.6943},{&quot;subaccount_id&quot;:1047,&quot;username&quot;:&quot;user5&quot;,&quot;total_count&quot;:&quot;1.00&quot;,&quot;total_price&quot;:0.2314}],
  post: [{&quot;subaccount_id&quot;:1039,&quot;username&quot;:&quot;user1&quot;,&quot;total_count&quot;:&quot;10&quot;,&quot;total_price&quot;:8.5624},{&quot;subaccount_id&quot;:1047,&quot;username&quot;:&quot;user5&quot;,&quot;total_count&quot;:&quot;3&quot;,&quot;total_price&quot;:2.5586}],
  email: [{&quot;subaccount_id&quot;:1039,&quot;username&quot;:&quot;user1&quot;,&quot;total_count&quot;:3992,&quot;total_price&quot;:9.002},{&quot;subaccount_id&quot;:1047,&quot;username&quot;:&quot;user5&quot;,&quot;total_count&quot;:998,&quot;total_price&quot;:0}],
  email_transactional: [],
  postcards: [],
  sms_total: null,
  voice_total: null,
  fax_total: null,
  post_total: null,
  email_total: null,
  mms_total: null,
  email_transactional_total: null,
  postcards_total: null,
  _currency: null
)
```

