# ClickSend::GetStatisticsDataInnerDeviceInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **label** | **String** | Device name | [optional] |
| **count** | **Float** | Total number of clicks on the short URL where the recipient has the specified device name | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::GetStatisticsDataInnerDeviceInner.new(
  label: mobile,
  count: 2
)
```

