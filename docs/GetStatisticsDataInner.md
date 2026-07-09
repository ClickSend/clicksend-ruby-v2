# ClickSend::GetStatisticsDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **long_url_id** | **String** | ID of a URL under the specified source and source_id | [optional] |
| **links** | [**GetStatisticsDataInnerLinks**](GetStatisticsDataInnerLinks.md) |  | [optional] |
| **device** | [**Array&lt;GetStatisticsDataInnerDeviceInner&gt;**](GetStatisticsDataInnerDeviceInner.md) | Device statistics of the recipients that clicked the short URL | [optional] |
| **os** | [**Array&lt;GetStatisticsDataInnerDeviceInner&gt;**](GetStatisticsDataInnerDeviceInner.md) | OS statistics of the recipients that clicked the short URL | [optional] |
| **browser** | [**Array&lt;GetStatisticsDataInnerDeviceInner&gt;**](GetStatisticsDataInnerDeviceInner.md) | Browser statistics of the recipients that clicked the short URL | [optional] |
| **country** | [**Array&lt;GetStatisticsDataInnerDeviceInner&gt;**](GetStatisticsDataInnerDeviceInner.md) | Country statistics of the recipients that clicked the short URL | [optional] |
| **region** | [**Array&lt;GetStatisticsDataInnerDeviceInner&gt;**](GetStatisticsDataInnerDeviceInner.md) | Region statistics of the recipients that clicked the short URL | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::GetStatisticsDataInner.new(
  long_url_id: quick_sms-26d1bc9a-d858-4b93-9368-1f31377a78c5-5908b13f05e7318be49bd1cb3a693d7c,
  links: null,
  device: null,
  os: null,
  browser: null,
  country: null,
  region: null
)
```

