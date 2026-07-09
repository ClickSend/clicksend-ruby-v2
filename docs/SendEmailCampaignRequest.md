# ClickSend::SendEmailCampaignRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **subject** | **String** |  | [optional] |
| **from_email_address_id** | **String** |  | [optional] |
| **template_id** | **String** |  | [optional] |
| **list_id** | **String** |  | [optional] |
| **from_name** | **String** |  | [optional] |
| **draft** | **Integer** |  | [optional] |
| **custom_string** | **String** |  | [optional] |
| **body** | **String** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SendEmailCampaignRequest.new(
  name: null,
  subject: null,
  from_email_address_id: null,
  template_id: null,
  list_id: null,
  from_name: null,
  draft: null,
  custom_string: null,
  body: null
)
```

