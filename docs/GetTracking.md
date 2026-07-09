# ClickSend::GetTracking

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total** | **Float** | Total number of short URLs associated with the long URL ID | [optional] |
| **per_page** | **Float** | The limit of tracking data per page | [optional] |
| **current_page_size** | **Float** | The number of data in the current page | [optional] |
| **prev_page_url** | **String** | Link to the previous page. This attribute will not be present if there is no previous page. | [optional] |
| **next_page_url** | **String** | Link to the next page. This attribute will not be present if there is no next page. | [optional] |
| **data** | [**Array&lt;GetTrackingDataInner&gt;**](GetTrackingDataInner.md) | Tracking data of the short URLs associated with the specified long URL ID. Note that only the data from the most recent click of the recipient (country, region, device, browser, and os) is recorded. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::GetTracking.new(
  total: 500,
  per_page: 20,
  current_page_size: 1,
  prev_page_url: https://rest.clicksend.com/v3/short-url/tracking/quick_sms-4961a11d-45bb-4d34-9d23-98dc9b277c38-123456-caee6179deb28e135538cb74e2eca2bd?offset&#x3D;eyJsb25nX3VybF9pZCI6InNtc19jYW1wYWlnbi00OTYxYTExZC00NWJiLTRkMzQtOWQyMy05OGRjOWIyNzdjMzgtMTIzNDU2LWNhZWU2MTc5ZGViMjhlMTM1NTM4Y2I3NGUyZWNhMmJkIiwic2hvcnRfdXJsIjoic21zdS5pby9EdXBOR1YifQ&amp;limit&#x3D;100&amp;direction&#x3D;backward,
  next_page_url: https://rest.clicksend.com/v3/short-url/tracking/quick_sms-4961a11d-45bb-4d34-9d23-98dc9b277c38-123456-caee6179deb28e135538cb74e2eca2bd?offset&#x3D;eyJsb25nX3VybF9pZCI6InNtc19jYW1wYWlnbi00OTYxYTExZC00NWJiLTRkMzQtOWQyMy05OGRjOWIyNzdjMzgtMTIzNDU2LWNhZWU2MTc5ZGViMjhlMTM1NTM4Y2I3NGUyZWNhMmJkIiwic2hvcnRfdXJsIjoic21zdS5pby9ROFVOdEcifQ&amp;limit&#x3D;100&amp;direction&#x3D;forward,
  data: null
)
```

