# ClickSend::MarkSmsReceiptAsReadRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **date_before** | **Integer** | The cutoff date. Receipts sent before this time will be marked as read. It’s in the &lt;a target&#x3D;\&quot;_blank\&quot; href&#x3D;\&quot;http://help.clicksend.com/what-is-a-unix-timestamp\&quot;&gt;Unix format&lt;/a&gt;. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::MarkSmsReceiptAsReadRequest.new(
  date_before: null
)
```

