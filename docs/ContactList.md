# ClickSend::ContactList

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **list_id** | **Integer** | The unique identifier for the list. | [optional] |
| **list_name** | **String** | The name of the list. | [optional] |
| **list_email_id** | **String** | The email address id of the list. | [optional] |
| **_contacts_count** | **Integer** | The number of contacts in the list. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ContactList.new(
  list_id: 428,
  list_name: ListCT3QrVL4od,
  list_email_id: KB0LHD6WXFVHZWTR,
  _contacts_count: 0
)
```

