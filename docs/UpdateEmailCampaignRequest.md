# ClickSend::UpdateEmailCampaignRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **schedule** | **Integer** |  | [optional] |
| **list_id** | **Integer** |  | [optional] |
| **subject** | **String** |  | [optional] |
| **from_email_address_id** | **Integer** |  | [optional] |
| **name** | **String** |  | [optional] |
| **template_id** | **Integer** |  | [optional] |
| **body** | **String** |  | [optional] |
| **from_name** | **String** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::UpdateEmailCampaignRequest.new(
  schedule: null,
  list_id: null,
  subject: null,
  from_email_address_id: null,
  name: null,
  template_id: null,
  body: null,
  from_name: null
)
```

