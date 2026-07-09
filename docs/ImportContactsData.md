# ClickSend::ImportContactsData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **msg** | **String** | The message to display. | [optional] |
| **ids** | **Array&lt;String&gt;** | The list of ids of the imported contacts. | [optional] |
| **id** | **String** | The list id of the imported contacts. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ImportContactsData.new(
  msg: Messages put on queue.,
  ids: [&quot;6254358460638066203&quot;],
  id: 6254358460638066203
)
```

