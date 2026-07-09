# ClickSend::ListCompliantSenderTypes200ResponseDataDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **recipient_country_code** | **String** | ISO 3166-1 alpha-2 formatted country code |  |
| **blocked_sender_types** | **Array&lt;String&gt;** | List of blocked sender types in recipient country |  |
| **allowed_sender_types** | [**Array&lt;ListCompliantSenderTypes200ResponseDataDataInnerAllowedSenderTypesInner&gt;**](ListCompliantSenderTypes200ResponseDataDataInnerAllowedSenderTypesInner.md) |  |  |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ListCompliantSenderTypes200ResponseDataDataInner.new(
  recipient_country_code: null,
  blocked_sender_types: null,
  allowed_sender_types: null
)
```

