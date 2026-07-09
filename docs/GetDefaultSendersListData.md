# ClickSend::GetDefaultSendersListData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **data** | [**Array&lt;DefaultSender&gt;**](DefaultSender.md) | List of default senders. | [optional] |
| **per_page** | **Integer** | Number of items per page. | [optional] |
| **self_page_url** | **String** | URL for the current page. | [optional] |
| **next_page_url** | **String** | URL for the next page. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::GetDefaultSendersListData.new(
  data: null,
  per_page: 1,
  self_page_url: https://api.clicksend.com/v4/sender_assignment_settings?offset&#x3D;f99872cc-11a6-48ba-a9f2-bcfb6dd1e3d4#8fa5ebc2-777b-45db-a448-ec76a40d4384&amp;per_page&#x3D;1,
  next_page_url: https://api.clicksend.com/v4/sender_assignment_settings?offset&#x3D;f99872cc-11a6-48ba-a9f2-bcfb6dd1e3d4#8fa5ebc2-777b-45db-a448-ec76a40d4384&amp;per_page&#x3D;1
)
```

