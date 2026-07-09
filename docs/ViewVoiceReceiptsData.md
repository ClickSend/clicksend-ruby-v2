# ClickSend::ViewVoiceReceiptsData

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
| **data** | [**Array&lt;VoiceReceipt&gt;**](VoiceReceipt.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewVoiceReceiptsData.new(
  total: 2,
  per_page: 15,
  current_page: 1,
  last_page: 1,
  next_page_url: null,
  prev_page_url: null,
  from: 1,
  to: 2,
  data: [{&quot;timestamp_send&quot;:&quot;1442381791&quot;,&quot;timestamp&quot;:&quot;1442381791&quot;,&quot;message_id&quot;:&quot;31BC271B-1E0C-45F6-9E7E-97186C46BB82&quot;,&quot;status_code&quot;:&quot;201&quot;,&quot;status_text&quot;:&quot;Success: Message received on handset.&quot;,&quot;error_code&quot;:null,&quot;error_text&quot;:null,&quot;custom_string&quot;:null,&quot;message_type&quot;:&quot;voice&quot;,&quot;digits&quot;:2},{&quot;timestamp_send&quot;:&quot;1442381829&quot;,&quot;timestamp&quot;:&quot;1442381829&quot;,&quot;message_id&quot;:&quot;23C8ADA3-FD8B-420B-801A-F829BB87AC6F&quot;,&quot;status_code&quot;:&quot;201&quot;,&quot;status_text&quot;:&quot;Success: Message received on handset.&quot;,&quot;error_code&quot;:null,&quot;error_text&quot;:null,&quot;custom_string&quot;:null,&quot;message_type&quot;:&quot;voice&quot;,&quot;digits&quot;:5}]
)
```

