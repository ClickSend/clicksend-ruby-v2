# ClickSend::ListOwnNumbersMetadataPagination

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **_self** | **String** | The URL of the current page. | [optional] |
| **_next** | **String** | The URL of the next page. | [optional] |
| **page_size** | **Integer** | The number of items returned per page. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ListOwnNumbersMetadataPagination.new(
  _self: https://rest.clicksend.com/v3/own-numbers?offset&#x3D;f99872cc-11a6-48ba-a9f2-bcfb6dd1e3d4#8fa5ebc2-777b-45db-a448-ec76a40d4384&amp;page_size&#x3D;10,
  _next: https://rest.clicksend.com/v3/own-numbers?offset&#x3D;f99872cc-11a6-48ba-a9f2-bcfb6dd1e3d4#8fa5ebc2-777b-45db-a448-ec76a40d4384&amp;page_size&#x3D;10,
  page_size: 10
)
```

