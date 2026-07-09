# ClickSend::MasterEmailTemplateThumbnail

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **small** | **String** | The small thumbnail of the template. | [optional] |
| **large** | **String** | The large thumbnail of the template. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::MasterEmailTemplateThumbnail.new(
  small: https://s3-ap-southeast-2.amazonaws.com/clicksend-api-downloads/_email-marketing/_templates-master/basic2/thumb-small.jpg,
  large: https://s3-ap-southeast-2.amazonaws.com/clicksend-api-downloads/_email-marketing/_templates-master/basic2/thumb-large.jpg
)
```

