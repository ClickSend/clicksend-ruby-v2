# ClickSend::Attachment

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **file_name** | **String** | The name of the attached file. | [optional] |
| **content_type** | **String** | The MIME type of the attached file. | [optional] |
| **content_disposition** | **String** | The content disposition of the attached file. | [optional] |
| **content_id** | **String** | The content ID of the attached file. | [optional] |
| **_attachment_file_url** | **String** | The URL to download the attached file. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::Attachment.new(
  file_name: null,
  content_type: null,
  content_disposition: null,
  content_id: null,
  _attachment_file_url: null
)
```

