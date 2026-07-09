# ClickSend::ContactsApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**delete_contact**](ContactsApi.md#delete_contact) | **DELETE** /v3/lists/{list_id}/contacts/{contact_id} | Delete Contact |
| [**get_specific_contact**](ContactsApi.md#get_specific_contact) | **GET** /v3/lists/{list_id}/contacts/{contact_id} | Get Specific Contact |
| [**update_contact**](ContactsApi.md#update_contact) | **PUT** /v3/lists/{list_id}/contacts/{contact_id} | Update Contact |


## delete_contact

> <DeleteContact> delete_contact(list_id, contact_id, opts)

Delete Contact

_Delete a contact_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | list_id | path | integer(int32) | true | List ID | | contact_id | path | integer(int32) | true | Contact ID |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::ContactsApi.new
list_id = 'list_id_example' # String | 
contact_id = 'contact_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Delete Contact
  result = api_instance.delete_contact(list_id, contact_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ContactsApi->delete_contact: #{e}"
end
```

#### Using the delete_contact_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteContact>, Integer, Hash)> delete_contact_with_http_info(list_id, contact_id, opts)

```ruby
begin
  # Delete Contact
  data, status_code, headers = api_instance.delete_contact_with_http_info(list_id, contact_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteContact>
rescue ClickSend::ApiError => e
  puts "Error when calling ContactsApi->delete_contact_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **list_id** | **String** |  |  |
| **contact_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**DeleteContact**](DeleteContact.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_specific_contact

> <GetSpecificContact> get_specific_contact(list_id, contact_id, opts)

Get Specific Contact

_Get a specific contact_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | list_id | path | integer(int32) | true | Your contact list id you want to access. | | contact_id | path | integer(int32) | true | Your contact id you want to access. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::ContactsApi.new
list_id = 'list_id_example' # String | 
contact_id = 'contact_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Get Specific Contact
  result = api_instance.get_specific_contact(list_id, contact_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ContactsApi->get_specific_contact: #{e}"
end
```

#### Using the get_specific_contact_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetSpecificContact>, Integer, Hash)> get_specific_contact_with_http_info(list_id, contact_id, opts)

```ruby
begin
  # Get Specific Contact
  data, status_code, headers = api_instance.get_specific_contact_with_http_info(list_id, contact_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetSpecificContact>
rescue ClickSend::ApiError => e
  puts "Error when calling ContactsApi->get_specific_contact_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **list_id** | **String** |  |  |
| **contact_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**GetSpecificContact**](GetSpecificContact.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_contact

> <UpdateContact> update_contact(list_id, contact_id, opts)

Update Contact

_Update specific contact_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | list_id | path | integer(int32) | true | Contact list id | | contact_id | path | integer(int32) | true | Contact ID |  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | phone_number | string | true | none | Your phone number in [E.164](https://en.wikipedia.org/wiki/E.164) format. Must be provided if no fax number or email. | | email | string | false | none | Your email. Must be provided if no phone number or fax number. | | fax_number | string | false | none | Your fax number. Must be provided if no phone number or email. | | first_name | string | false | none | Your first name. | | address_line_1 | string | false | none | Your street address | | address_line_2 | string | false | none | none | | address_city | string | false | none | Your nearest city | | address_state | string | false | none | Your current state | | address_postal_code | string | false | none | Your current postcode | | address_country | string | false | none | Your current country | | organization_name | string | false | none | Your organisation name | | custom_1 | string | true | none | none | | custom_2 | string | false | none | none | | custom_3 | string | false | none | none | | custom_4 | string | false | none | none | | last_name | string | false | none | Your last name |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::ContactsApi.new
list_id = 'list_id_example' # String | 
contact_id = 'contact_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  create_new_contact_request: ClickSend::CreateNewContactRequest.new # CreateNewContactRequest | 
}

begin
  # Update Contact
  result = api_instance.update_contact(list_id, contact_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ContactsApi->update_contact: #{e}"
end
```

#### Using the update_contact_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateContact>, Integer, Hash)> update_contact_with_http_info(list_id, contact_id, opts)

```ruby
begin
  # Update Contact
  data, status_code, headers = api_instance.update_contact_with_http_info(list_id, contact_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateContact>
rescue ClickSend::ApiError => e
  puts "Error when calling ContactsApi->update_contact_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **list_id** | **String** |  |  |
| **contact_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **create_new_contact_request** | [**CreateNewContactRequest**](CreateNewContactRequest.md) |  | [optional] |

### Return type

[**UpdateContact**](UpdateContact.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

