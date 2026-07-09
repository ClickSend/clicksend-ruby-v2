# ClickSend::CancelEmailCampaignRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **subject** | **String** |  | [optional] |
| **from_email_address_id** | **Integer** |  | [optional] |
| **template_id** | **Integer** |  | [optional] |
| **list_id** | **Integer** |  | [optional] |
| **from_name** | **String** |  | [optional] |
| **draft** | **Integer** |  | [optional] |
| **schedule** | **String** |  | [optional] |
| **custom_string** | **String** |  | [optional] |
| **body** | **String** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CancelEmailCampaignRequest.new(
  name: null,
  subject: null,
  from_email_address_id: null,
  template_id: null,
  list_id: null,
  from_name: null,
  draft: null,
  schedule: null,
  custom_string: null,
  body: null
)
```

