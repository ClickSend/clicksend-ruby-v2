# ClickSend::ListsApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**copy_contact_to_list**](ListsApi.md#copy_contact_to_list) | **PUT** /v3/lists/{from_list_id}/contacts/{contact_id}/copy/{to_list_id} | Copy Contact to List |
| [**create_list**](ListsApi.md#create_list) | **POST** /v3/lists | Create List |
| [**create_new_contact**](ListsApi.md#create_new_contact) | **POST** /v3/lists/{list_id}/contacts | Create New Contact |
| [**delete_list**](ListsApi.md#delete_list) | **DELETE** /v3/lists/{list_id} | Delete List |
| [**import_contacts**](ListsApi.md#import_contacts) | **POST** /v3/lists/{list_id}/import | Import Contacts |
| [**remove_duplicate_contacts**](ListsApi.md#remove_duplicate_contacts) | **PUT** /v3/lists/{list_id}/remove-duplicates/ | Remove Duplicate Contacts |
| [**remove_opted_out_contacts**](ListsApi.md#remove_opted_out_contacts) | **PUT** /v3/lists/{list_id}/remove-opted-out-contacts/{opt_out_list_id} | Remove Opted Out Contacts |
| [**transfer_contact_to_list**](ListsApi.md#transfer_contact_to_list) | **PUT** /v3/lists/{from_list_id}/contacts/{contact_id}/transfer/{to_list_id} | Transfer Contact to List |
| [**update_list**](ListsApi.md#update_list) | **PUT** /v3/lists/{list_id} | Update List |
| [**view_contact_lists**](ListsApi.md#view_contact_lists) | **GET** /v3/search/contacts-lists | View Contact Lists |
| [**view_list_contacts**](ListsApi.md#view_list_contacts) | **GET** /v3/lists/{list_id}/contacts | View List Contacts |
| [**view_lists**](ListsApi.md#view_lists) | **GET** /v3/lists | View Lists |
| [**view_specific_list**](ListsApi.md#view_specific_list) | **GET** /v3/lists/{list_id} | View Specific List |


## copy_contact_to_list

> <CopyContactToList> copy_contact_to_list(from_list_id, contact_id, to_list_id, opts)

Copy Contact to List

_Copy contact to another list_  Copy contact to another list  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | from_list_id | path | integer(int32) | true | List ID for list that contains contact. | | contact_id | path | integer(int32) | true | Contact ID | | to_list_id | path | integer(int32) | true | List ID for list you want to copy contact to. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

### Examples

```ruby
require 'time'
require 'clicksend'
# setup authorization
ClickSend.configure do |config|
  # Configure HTTP basic authorization: basicAuth
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = ClickSend::ListsApi.new
from_list_id = 'from_list_id_example' # String | 
contact_id = 'contact_id_example' # String | 
to_list_id = 'to_list_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  body: { ... } # Object | 
}

begin
  # Copy Contact to List
  result = api_instance.copy_contact_to_list(from_list_id, contact_id, to_list_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->copy_contact_to_list: #{e}"
end
```

#### Using the copy_contact_to_list_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CopyContactToList>, Integer, Hash)> copy_contact_to_list_with_http_info(from_list_id, contact_id, to_list_id, opts)

```ruby
begin
  # Copy Contact to List
  data, status_code, headers = api_instance.copy_contact_to_list_with_http_info(from_list_id, contact_id, to_list_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CopyContactToList>
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->copy_contact_to_list_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **from_list_id** | **String** |  |  |
| **contact_id** | **String** |  |  |
| **to_list_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **body** | **Object** |  | [optional] |

### Return type

[**CopyContactToList**](CopyContactToList.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_list

> <CreateList> create_list(opts)

Create List

_Create new contact list_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | list_name | body | string | true | Your contact list name |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

### Examples

```ruby
require 'time'
require 'clicksend'
# setup authorization
ClickSend.configure do |config|
  # Configure HTTP basic authorization: basicAuth
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = ClickSend::ListsApi.new
opts = {
  content_type: 'application/json', # String | 
  create_list_request: ClickSend::CreateListRequest.new # CreateListRequest | 
}

begin
  # Create List
  result = api_instance.create_list(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->create_list: #{e}"
end
```

#### Using the create_list_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateList>, Integer, Hash)> create_list_with_http_info(opts)

```ruby
begin
  # Create List
  data, status_code, headers = api_instance.create_list_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateList>
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->create_list_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **create_list_request** | [**CreateListRequest**](CreateListRequest.md) |  | [optional] |

### Return type

[**CreateList**](CreateList.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_new_contact

> <CreateNewContact> create_new_contact(list_id, opts)

Create New Contact

_Create new contact_  ### parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | list_id | path | integer(int32) | true | List id | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |   ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | phone_number | string | true | none | Your phone number in\\_[E.164](https://en.wikipedia.org/wiki/E.164)\\_format. Must be provided if no fax number or email. | | email | string | false | none | Your email. Must be provided if no phone number or fax number. | | fax_number | string | false | none | Your fax number. Must be provided if no phone number or email. | | first_name | string | false | none | Your first name. | | address_line_1 | string | false | none | Your street address | | address_line_2 | string | false | none | none | | address_city | string | false | none | Your nearest city | | address_state | string | false | none | Your current state | | address_postal_code | string | false | none | Your current postcode | | address_country | string | false | none | Your current country | | organization_name | string | false | none | Your organisation name | | custom_1 | string | true | none | none | | custom_2 | string | false | none | none | | custom_3 | string | false | none | none | | custom_4 | string | false | none | none | | last_name | string | false | none | Your last name |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

### Examples

```ruby
require 'time'
require 'clicksend'
# setup authorization
ClickSend.configure do |config|
  # Configure HTTP basic authorization: basicAuth
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = ClickSend::ListsApi.new
list_id = 'list_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  create_new_contact_request: ClickSend::CreateNewContactRequest.new # CreateNewContactRequest | 
}

begin
  # Create New Contact
  result = api_instance.create_new_contact(list_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->create_new_contact: #{e}"
end
```

#### Using the create_new_contact_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateNewContact>, Integer, Hash)> create_new_contact_with_http_info(list_id, opts)

```ruby
begin
  # Create New Contact
  data, status_code, headers = api_instance.create_new_contact_with_http_info(list_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateNewContact>
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->create_new_contact_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **list_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **create_new_contact_request** | [**CreateNewContactRequest**](CreateNewContactRequest.md) |  | [optional] |

### Return type

[**CreateNewContact**](CreateNewContact.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_list

> <DeleteList> delete_list(list_id, opts)

Delete List

_ListsByListIdDelete_  Delete a specific contact list  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | list_id | path | integer(int32) | true | List ID |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

### Examples

```ruby
require 'time'
require 'clicksend'
# setup authorization
ClickSend.configure do |config|
  # Configure HTTP basic authorization: basicAuth
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = ClickSend::ListsApi.new
list_id = 'list_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Delete List
  result = api_instance.delete_list(list_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->delete_list: #{e}"
end
```

#### Using the delete_list_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteList>, Integer, Hash)> delete_list_with_http_info(list_id, opts)

```ruby
begin
  # Delete List
  data, status_code, headers = api_instance.delete_list_with_http_info(list_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteList>
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->delete_list_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **list_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**DeleteList**](DeleteList.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## import_contacts

> <ImportContacts> import_contacts(list_id, opts)

Import Contacts

_Import contacts to list_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | list_id | path | integer(int32) | true | Your contact list id you want to access. |  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | file_url | string | true | none | URL of file to process | | field_order | \\[string\\] | true | none | Order of fields in file |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

### Examples

```ruby
require 'time'
require 'clicksend'
# setup authorization
ClickSend.configure do |config|
  # Configure HTTP basic authorization: basicAuth
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = ClickSend::ListsApi.new
list_id = 'list_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  import_contacts_request: ClickSend::ImportContactsRequest.new # ImportContactsRequest | 
}

begin
  # Import Contacts
  result = api_instance.import_contacts(list_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->import_contacts: #{e}"
end
```

#### Using the import_contacts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ImportContacts>, Integer, Hash)> import_contacts_with_http_info(list_id, opts)

```ruby
begin
  # Import Contacts
  data, status_code, headers = api_instance.import_contacts_with_http_info(list_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ImportContacts>
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->import_contacts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **list_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **import_contacts_request** | [**ImportContactsRequest**](ImportContactsRequest.md) |  | [optional] |

### Return type

[**ImportContacts**](ImportContacts.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## remove_duplicate_contacts

> <RemoveDuplicateContacts> remove_duplicate_contacts(list_id, opts)

Remove Duplicate Contacts

_Remove duplicate contacts_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | list_id | path | integer(int32) | true | Your list id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

### Examples

```ruby
require 'time'
require 'clicksend'
# setup authorization
ClickSend.configure do |config|
  # Configure HTTP basic authorization: basicAuth
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = ClickSend::ListsApi.new
list_id = 'list_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  remove_duplicate_contacts_request: ClickSend::RemoveDuplicateContactsRequest.new # RemoveDuplicateContactsRequest | 
}

begin
  # Remove Duplicate Contacts
  result = api_instance.remove_duplicate_contacts(list_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->remove_duplicate_contacts: #{e}"
end
```

#### Using the remove_duplicate_contacts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RemoveDuplicateContacts>, Integer, Hash)> remove_duplicate_contacts_with_http_info(list_id, opts)

```ruby
begin
  # Remove Duplicate Contacts
  data, status_code, headers = api_instance.remove_duplicate_contacts_with_http_info(list_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RemoveDuplicateContacts>
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->remove_duplicate_contacts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **list_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **remove_duplicate_contacts_request** | [**RemoveDuplicateContactsRequest**](RemoveDuplicateContactsRequest.md) |  | [optional] |

### Return type

[**RemoveDuplicateContacts**](RemoveDuplicateContacts.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## remove_opted_out_contacts

> <RemoveOptedOutContacts> remove_opted_out_contacts(list_id, opt_out_list_id, opts)

Remove Opted Out Contacts

_Remove all opted out contacts_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | list_id | path | integer(int32) | true | Your list id | | opt_out_list_id | path | integer(int32) | true | Your opt out list id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

### Examples

```ruby
require 'time'
require 'clicksend'
# setup authorization
ClickSend.configure do |config|
  # Configure HTTP basic authorization: basicAuth
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = ClickSend::ListsApi.new
list_id = 'list_id_example' # String | 
opt_out_list_id = 'opt_out_list_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  body: { ... } # Object | 
}

begin
  # Remove Opted Out Contacts
  result = api_instance.remove_opted_out_contacts(list_id, opt_out_list_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->remove_opted_out_contacts: #{e}"
end
```

#### Using the remove_opted_out_contacts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RemoveOptedOutContacts>, Integer, Hash)> remove_opted_out_contacts_with_http_info(list_id, opt_out_list_id, opts)

```ruby
begin
  # Remove Opted Out Contacts
  data, status_code, headers = api_instance.remove_opted_out_contacts_with_http_info(list_id, opt_out_list_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RemoveOptedOutContacts>
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->remove_opted_out_contacts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **list_id** | **String** |  |  |
| **opt_out_list_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **body** | **Object** |  | [optional] |

### Return type

[**RemoveOptedOutContacts**](RemoveOptedOutContacts.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## transfer_contact_to_list

> <TransferContactToList> transfer_contact_to_list(from_list_id, contact_id, to_list_id, opts)

Transfer Contact to List

_Transfer contact to another list_  Transfer contact to another list  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | from_list_id | path | integer(int32) | true | List ID for list that contains contact. | | contact_id | path | integer(int32) | true | Contact ID | | to_list_id | path | integer(int32) | true | List ID for list you want to transfer contact to. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

### Examples

```ruby
require 'time'
require 'clicksend'
# setup authorization
ClickSend.configure do |config|
  # Configure HTTP basic authorization: basicAuth
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = ClickSend::ListsApi.new
from_list_id = 'from_list_id_example' # String | 
contact_id = 'contact_id_example' # String | 
to_list_id = 'to_list_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  body: { ... } # Object | 
}

begin
  # Transfer Contact to List
  result = api_instance.transfer_contact_to_list(from_list_id, contact_id, to_list_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->transfer_contact_to_list: #{e}"
end
```

#### Using the transfer_contact_to_list_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TransferContactToList>, Integer, Hash)> transfer_contact_to_list_with_http_info(from_list_id, contact_id, to_list_id, opts)

```ruby
begin
  # Transfer Contact to List
  data, status_code, headers = api_instance.transfer_contact_to_list_with_http_info(from_list_id, contact_id, to_list_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TransferContactToList>
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->transfer_contact_to_list_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **from_list_id** | **String** |  |  |
| **contact_id** | **String** |  |  |
| **to_list_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **body** | **Object** |  | [optional] |

### Return type

[**TransferContactToList**](TransferContactToList.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_list

> <UpdateList> update_list(list_id, opts)

Update List

_Update specific contact list_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | list_id | path | integer(int32) | true | Your list id | | list_name | body | string | true | Your new list name |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

### Examples

```ruby
require 'time'
require 'clicksend'
# setup authorization
ClickSend.configure do |config|
  # Configure HTTP basic authorization: basicAuth
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = ClickSend::ListsApi.new
list_id = 'list_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  create_list_request: ClickSend::CreateListRequest.new # CreateListRequest | 
}

begin
  # Update List
  result = api_instance.update_list(list_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->update_list: #{e}"
end
```

#### Using the update_list_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateList>, Integer, Hash)> update_list_with_http_info(list_id, opts)

```ruby
begin
  # Update List
  data, status_code, headers = api_instance.update_list_with_http_info(list_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateList>
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->update_list_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **list_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **create_list_request** | [**CreateListRequest**](CreateListRequest.md) |  | [optional] |

### Return type

[**UpdateList**](UpdateList.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## view_contact_lists

> view_contact_lists(opts)

View Contact Lists

_Get list of searched contact list_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | q | query | string | true | Your keyword or query. | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  This endpoint requires authentication, [more info...](/#authentication)

### Examples

```ruby
require 'time'
require 'clicksend'
# setup authorization
ClickSend.configure do |config|
  # Configure HTTP basic authorization: basicAuth
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = ClickSend::ListsApi.new
opts = {
  q: 'Test' # String | 
}

begin
  # View Contact Lists
  api_instance.view_contact_lists(opts)
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->view_contact_lists: #{e}"
end
```

#### Using the view_contact_lists_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> view_contact_lists_with_http_info(opts)

```ruby
begin
  # View Contact Lists
  data, status_code, headers = api_instance.view_contact_lists_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->view_contact_lists_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **q** | **String** |  | [optional] |

### Return type

nil (empty response body)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_list_contacts

> <ViewListContacts> view_list_contacts(list_id, opts)

View List Contacts

_Get all contacts in a list_  ### parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | list_id | path | integer(int32) | true | Contact list ID | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) | | updated_after | query | integer(int32) | false | Get all contacts updated after a given timestamp. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

### Examples

```ruby
require 'time'
require 'clicksend'
# setup authorization
ClickSend.configure do |config|
  # Configure HTTP basic authorization: basicAuth
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = ClickSend::ListsApi.new
list_id = 'list_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View List Contacts
  result = api_instance.view_list_contacts(list_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->view_list_contacts: #{e}"
end
```

#### Using the view_list_contacts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewListContacts>, Integer, Hash)> view_list_contacts_with_http_info(list_id, opts)

```ruby
begin
  # View List Contacts
  data, status_code, headers = api_instance.view_list_contacts_with_http_info(list_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewListContacts>
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->view_list_contacts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **list_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewListContacts**](ViewListContacts.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_lists

> <ViewLists> view_lists(opts)

View Lists

_Get all contact lists_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

### Examples

```ruby
require 'time'
require 'clicksend'
# setup authorization
ClickSend.configure do |config|
  # Configure HTTP basic authorization: basicAuth
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = ClickSend::ListsApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Lists
  result = api_instance.view_lists(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->view_lists: #{e}"
end
```

#### Using the view_lists_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewLists>, Integer, Hash)> view_lists_with_http_info(opts)

```ruby
begin
  # View Lists
  data, status_code, headers = api_instance.view_lists_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewLists>
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->view_lists_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewLists**](ViewLists.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_specific_list

> <ViewSpecificList> view_specific_list(list_id, opts)

View Specific List

_Get specific contact list_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | list_id | path | integer(int32) | true | List ID |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

### Examples

```ruby
require 'time'
require 'clicksend'
# setup authorization
ClickSend.configure do |config|
  # Configure HTTP basic authorization: basicAuth
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = ClickSend::ListsApi.new
list_id = 'list_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Specific List
  result = api_instance.view_specific_list(list_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->view_specific_list: #{e}"
end
```

#### Using the view_specific_list_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewSpecificList>, Integer, Hash)> view_specific_list_with_http_info(list_id, opts)

```ruby
begin
  # View Specific List
  data, status_code, headers = api_instance.view_specific_list_with_http_info(list_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewSpecificList>
rescue ClickSend::ApiError => e
  puts "Error when calling ListsApi->view_specific_list_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **list_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewSpecificList**](ViewSpecificList.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

