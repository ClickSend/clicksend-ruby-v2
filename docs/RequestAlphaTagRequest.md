# ClickSend::RequestAlphaTagRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **alpha_tag** | **String** |  | [optional] |
| **reason** | **String** |  | [optional] |
| **countries** | **Array&lt;String&gt;** |  | [optional] |
| **businesses** | [**Array&lt;RequestAlphaTagRequestBusinessesInner&gt;**](RequestAlphaTagRequestBusinessesInner.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::RequestAlphaTagRequest.new(
  alpha_tag: null,
  reason: null,
  countries: null,
  businesses: null
)
```

