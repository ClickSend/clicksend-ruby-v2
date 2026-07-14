# ClickSend::ViewListsData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total** | **Integer** | The total number of contacts in the list. | [optional] |
| **per_page** | **Integer** | The number of contacts returned per page. | [optional] |
| **current_page** | **Integer** | The current page number. | [optional] |
| **last_page** | **Integer** | The total number of pages. | [optional] |
| **next_page_url** | **String** | The URL of the next page of contacts. | [optional] |
| **prev_page_url** | **String** | The URL of the previous page of contacts. | [optional] |
| **from** | **Integer** | The number of the first contact on the current page. | [optional] |
| **to** | **Integer** | The number of the last contact on the current page. | [optional] |
| **first_page_url** | **String** | The URL of the first page of records. | [optional] |
| **last_page_url** | **String** | The URL of the last page of records. | [optional] |
| **path** | **String** | The base URL path used to build pagination links. | [optional] |
| **links** | [**Array&lt;ViewListsDataLinksInner&gt;**](ViewListsDataLinksInner.md) | The list of pagination links. | [optional] |
| **data** | [**Array&lt;ContactList&gt;**](ContactList.md) | The contacts in the list. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewListsData.new(
  total: 0,
  per_page: 10,
  current_page: 1,
  last_page: 2,
  next_page_url: https://api.clicksend.com/v3/lists?page&#x3D;2,
  prev_page_url: https://api.clicksend.com/v3/lists?page&#x3D;1,
  from: 1,
  to: 10,
  first_page_url: https://rest.clicksend.com/v3/lists?page&#x3D;1,
  last_page_url: https://rest.clicksend.com/v3/lists?page&#x3D;2,
  path: https://rest.clicksend.com/v3/lists,
  links: null,
  data: [{&quot;list_id&quot;:428,&quot;list_name&quot;:&quot;ListCT3QrVL4od&quot;,&quot;list_email_id&quot;:&quot;KB0LHD6WXFVHZWTR&quot;,&quot;_contacts_count&quot;:0},{&quot;list_id&quot;:429,&quot;list_name&quot;:&quot;ListCT3QrVL4od&quot;,&quot;list_email_id&quot;:&quot;KB0LHD6WXFVHZWTR&quot;,&quot;_contacts_count&quot;:0}]
)
```

