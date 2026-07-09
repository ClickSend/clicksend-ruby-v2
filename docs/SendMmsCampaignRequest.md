# ClickSend::SendMmsCampaignRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **list_id** | **String** |  | [optional] |
| **name** | **String** |  | [optional] |
| **from** | **String** |  | [optional] |
| **body** | **String** |  | [optional] |
| **url_to_shorten** | **String** |  | [optional] |
| **subject** | **String** |  | [optional] |
| **media_file** | **String** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SendMmsCampaignRequest.new(
  list_id: null,
  name: null,
  from: null,
  body: null,
  url_to_shorten: null,
  subject: null,
  media_file: null
)
```

