# ClickSend::GetTrackingDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **open_count** | **Float** | Number of times the short URL was opened | [optional] |
| **date_opened** | **Float** | Date in unix seconds when the short URL was first opened. Null if the short URL was never opened. | [optional] |
| **user_geo_country** | **String** | Country where the recipient is located when the short URL was opened. Null if the short URL was never opened. | [optional] |
| **user_geo_region** | **String** | Geographical region where the recipient is located when the short URL was opened. Null if the short URL was never opened. | [optional] |
| **user_device** | **String** | Deviced used by the recipient to open the short URL. Null if the short URL was never opened. | [optional] |
| **user_browser** | **String** | Browser used by the recipient to open the short URL. Null if the short URL was never opened. | [optional] |
| **user_os** | **String** | Opearating system used by the recipient to open the short URL. Null if the short URL was never opened. | [optional] |
| **contact** | [**GetTrackingDataInnerContact**](GetTrackingDataInnerContact.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::GetTrackingDataInner.new(
  open_count: 5,
  date_opened: 1733981414,
  user_geo_country: AU,
  user_geo_region: western_australia,
  user_device: mobile,
  user_browser: chrome,
  user_os: android,
  contact: null
)
```

