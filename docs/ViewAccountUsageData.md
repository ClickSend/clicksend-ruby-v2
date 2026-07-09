# ClickSend::ViewAccountUsageData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **sms** | [**Array&lt;ViewAccountUsageDataSmsInner&gt;**](ViewAccountUsageDataSmsInner.md) |  | [optional] |
| **voice** | [**Array&lt;ViewAccountUsageDataSmsInner&gt;**](ViewAccountUsageDataSmsInner.md) |  | [optional] |
| **fax** | [**Array&lt;ViewAccountUsageDataSmsInner&gt;**](ViewAccountUsageDataSmsInner.md) |  | [optional] |
| **post** | [**Array&lt;ViewAccountUsageDataSmsInner&gt;**](ViewAccountUsageDataSmsInner.md) |  | [optional] |
| **email** | [**Array&lt;ViewAccountUsageDataEmailInner&gt;**](ViewAccountUsageDataEmailInner.md) |  | [optional] |
| **sms_total** | [**ViewAccountUsageDataSmsTotal**](ViewAccountUsageDataSmsTotal.md) |  | [optional] |
| **voice_total** | [**ViewAccountUsageDataSmsTotal**](ViewAccountUsageDataSmsTotal.md) |  | [optional] |
| **fax_total** | [**ViewAccountUsageDataSmsTotal**](ViewAccountUsageDataSmsTotal.md) |  | [optional] |
| **post_total** | [**ViewAccountUsageDataSmsTotal**](ViewAccountUsageDataSmsTotal.md) |  | [optional] |
| **email_total** | [**ViewVoiceStatisticsDataTotalOutbound**](ViewVoiceStatisticsDataTotalOutbound.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewAccountUsageData.new(
  sms: [{&quot;subaccount_id&quot;:1039,&quot;username&quot;:&quot;gerald&quot;,&quot;total_count&quot;:&quot;29.00&quot;,&quot;total_price&quot;:&quot;2.1337&quot;},{&quot;subaccount_id&quot;:1047,&quot;username&quot;:&quot;user5&quot;,&quot;total_count&quot;:&quot;4.00&quot;,&quot;total_price&quot;:&quot;0.3080&quot;}],
  voice: [{&quot;subaccount_id&quot;:1039,&quot;username&quot;:&quot;user1&quot;,&quot;total_count&quot;:&quot;6.00&quot;,&quot;total_price&quot;:&quot;0.1980&quot;},{&quot;subaccount_id&quot;:1047,&quot;username&quot;:&quot;user5&quot;,&quot;total_count&quot;:&quot;1.00&quot;,&quot;total_price&quot;:&quot;0.0330&quot;}],
  fax: [{&quot;subaccount_id&quot;:1039,&quot;username&quot;:&quot;user1&quot;,&quot;total_count&quot;:&quot;3.00&quot;,&quot;total_price&quot;:&quot;0.6943&quot;},{&quot;subaccount_id&quot;:1047,&quot;username&quot;:&quot;user5&quot;,&quot;total_count&quot;:&quot;1.00&quot;,&quot;total_price&quot;:&quot;0.2314&quot;}],
  post: [{&quot;subaccount_id&quot;:1039,&quot;username&quot;:&quot;user1&quot;,&quot;total_count&quot;:&quot;10&quot;,&quot;total_price&quot;:&quot;8.5624&quot;},{&quot;subaccount_id&quot;:1047,&quot;username&quot;:&quot;user5&quot;,&quot;total_count&quot;:&quot;3&quot;,&quot;total_price&quot;:&quot;2.5586&quot;}],
  email: [{&quot;subaccount_id&quot;:1039,&quot;username&quot;:&quot;user1&quot;,&quot;total_count&quot;:3992,&quot;total_price&quot;:&quot;9.0020&quot;},{&quot;subaccount_id&quot;:1047,&quot;username&quot;:&quot;user5&quot;,&quot;total_count&quot;:998,&quot;total_price&quot;:&quot;0.0000&quot;}],
  sms_total: null,
  voice_total: null,
  fax_total: null,
  post_total: null,
  email_total: null
)
```

