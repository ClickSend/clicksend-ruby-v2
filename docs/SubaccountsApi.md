# ClickSend::SubaccountsApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_subaccount**](SubaccountsApi.md#create_subaccount) | **POST** /v3/subaccounts | Create Subaccount |
| [**delete_subaccount**](SubaccountsApi.md#delete_subaccount) | **DELETE** /v3/subaccounts/{subaccount_id} | Delete Subaccount |
| [**generate_new_api_key**](SubaccountsApi.md#generate_new_api_key) | **PUT** /v3/subaccounts/{subaccount_id}/regen-api-key | Generate New API Key |
| [**update_subaccount**](SubaccountsApi.md#update_subaccount) | **PUT** /v3/subaccounts/{subaccount_id} | Update Subaccount |
| [**view_specific_subaccount**](SubaccountsApi.md#view_specific_subaccount) | **GET** /v3/subaccounts/{subaccount_id} | View Specific Subaccount |
| [**view_subaccounts**](SubaccountsApi.md#view_subaccounts) | **GET** /v3/subaccounts | View Subaccounts |


## create_subaccount

> <CreateSubaccount> create_subaccount(opts)

Create Subaccount

_Create new subaccount_  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | api_username | string | true | none | Your new api username. | | password | string | true | none | Your new password | | email | string | true | none | Your new email. | | phone_number | string | true | none | Your phone number in [E.164](https://en.wikipedia.org/wiki/E.164) format. | | first_name | string | true | none | Your firstname | | last_name | string | true | none | Your lastname | | access_users | integer(int1) | false | none | Flag value must be 1 for yes or 0 for no. | | access_billing | integer(int1) | false | none | Flag value must be 1 for yes or 0 for no. | | access_reporting | integer(int1) | false | none | Flag value must be 1 for yes or 0 for no. | | access_contacts | integer(int1) | false | none | Flag value must be 1 for yes or 0 for no. | | access_settings | integer(int1) | false | none | Flag value must be 1 for yes or 0 for no. |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SubaccountsApi.new
opts = {
  content_type: 'application/json', # String | 
  create_subaccount_request: ClickSend::CreateSubaccountRequest.new # CreateSubaccountRequest | 
}

begin
  # Create Subaccount
  result = api_instance.create_subaccount(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SubaccountsApi->create_subaccount: #{e}"
end
```

#### Using the create_subaccount_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateSubaccount>, Integer, Hash)> create_subaccount_with_http_info(opts)

```ruby
begin
  # Create Subaccount
  data, status_code, headers = api_instance.create_subaccount_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateSubaccount>
rescue ClickSend::ApiError => e
  puts "Error when calling SubaccountsApi->create_subaccount_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **create_subaccount_request** | [**CreateSubaccountRequest**](CreateSubaccountRequest.md) |  | [optional] |

### Return type

[**CreateSubaccount**](CreateSubaccount.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_subaccount

> <DeleteSubaccount> delete_subaccount(subaccount_id, opts)

Delete Subaccount

_Delete a subaccount_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | subaccount_id | path | integer(int32) | true | ID of subaccount to delete |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SubaccountsApi.new
subaccount_id = 'subaccount_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Delete Subaccount
  result = api_instance.delete_subaccount(subaccount_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SubaccountsApi->delete_subaccount: #{e}"
end
```

#### Using the delete_subaccount_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteSubaccount>, Integer, Hash)> delete_subaccount_with_http_info(subaccount_id, opts)

```ruby
begin
  # Delete Subaccount
  data, status_code, headers = api_instance.delete_subaccount_with_http_info(subaccount_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteSubaccount>
rescue ClickSend::ApiError => e
  puts "Error when calling SubaccountsApi->delete_subaccount_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **subaccount_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**DeleteSubaccount**](DeleteSubaccount.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## generate_new_api_key

> <GenerateNewApiKey> generate_new_api_key(subaccount_id, opts)

Generate New API Key

_Regenerate an API Key_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | subaccount_id | path | integer(int32) | true | ID of subaccount to regenerate API key for |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SubaccountsApi.new
subaccount_id = 'subaccount_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  generate_new_api_key_request: ClickSend::GenerateNewApiKeyRequest.new # GenerateNewApiKeyRequest | 
}

begin
  # Generate New API Key
  result = api_instance.generate_new_api_key(subaccount_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SubaccountsApi->generate_new_api_key: #{e}"
end
```

#### Using the generate_new_api_key_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GenerateNewApiKey>, Integer, Hash)> generate_new_api_key_with_http_info(subaccount_id, opts)

```ruby
begin
  # Generate New API Key
  data, status_code, headers = api_instance.generate_new_api_key_with_http_info(subaccount_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GenerateNewApiKey>
rescue ClickSend::ApiError => e
  puts "Error when calling SubaccountsApi->generate_new_api_key_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **subaccount_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **generate_new_api_key_request** | [**GenerateNewApiKeyRequest**](GenerateNewApiKeyRequest.md) |  | [optional] |

### Return type

[**GenerateNewApiKey**](GenerateNewApiKey.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_subaccount

> <UpdateSubaccount> update_subaccount(subaccount_id, opts)

Update Subaccount

_Update subaccount_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | subaccount_id | path | integer(int32) | true | ID of subaccount to update |  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | api_username | string | true | none | Your new api username. | | password | string | true | none | Your new password | | email | string | true | none | Your new email. | | phone_number | string | true | none | Your phone number in [E.164](https://en.wikipedia.org/wiki/E.164) format. | | first_name | string | true | none | Your firstname | | last_name | string | true | none | Your lastname | | access_users | integer(int1) | false | none | Flag value must be 1 for yes or 0 for no. | | access_billing | integer(int1) | false | none | Flag value must be 1 for yes or 0 for no. | | access_reporting | integer(int1) | false | none | Flag value must be 1 for yes or 0 for no. | | access_contacts | integer(int1) | false | none | Flag value must be 1 for yes or 0 for no. | | access_settings | integer(int1) | false | none | Flag value must be 1 for yes or 0 for no. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SubaccountsApi.new
subaccount_id = 'subaccount_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  update_subaccount_request: ClickSend::UpdateSubaccountRequest.new # UpdateSubaccountRequest | 
}

begin
  # Update Subaccount
  result = api_instance.update_subaccount(subaccount_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SubaccountsApi->update_subaccount: #{e}"
end
```

#### Using the update_subaccount_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateSubaccount>, Integer, Hash)> update_subaccount_with_http_info(subaccount_id, opts)

```ruby
begin
  # Update Subaccount
  data, status_code, headers = api_instance.update_subaccount_with_http_info(subaccount_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateSubaccount>
rescue ClickSend::ApiError => e
  puts "Error when calling SubaccountsApi->update_subaccount_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **subaccount_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **update_subaccount_request** | [**UpdateSubaccountRequest**](UpdateSubaccountRequest.md) |  | [optional] |

### Return type

[**UpdateSubaccount**](UpdateSubaccount.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## view_specific_subaccount

> <ViewSpecificSubaccount> view_specific_subaccount(subaccount_id, opts)

View Specific Subaccount

_Get specific subaccount_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | subaccount_id | path | integer(int32) | true | ID of subaccount to get |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SubaccountsApi.new
subaccount_id = 'subaccount_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Specific Subaccount
  result = api_instance.view_specific_subaccount(subaccount_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SubaccountsApi->view_specific_subaccount: #{e}"
end
```

#### Using the view_specific_subaccount_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewSpecificSubaccount>, Integer, Hash)> view_specific_subaccount_with_http_info(subaccount_id, opts)

```ruby
begin
  # View Specific Subaccount
  data, status_code, headers = api_instance.view_specific_subaccount_with_http_info(subaccount_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewSpecificSubaccount>
rescue ClickSend::ApiError => e
  puts "Error when calling SubaccountsApi->view_specific_subaccount_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **subaccount_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewSpecificSubaccount**](ViewSpecificSubaccount.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_subaccounts

> <ViewSubaccounts> view_subaccounts(opts)

View Subaccounts

_Get all subaccounts_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SubaccountsApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Subaccounts
  result = api_instance.view_subaccounts(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SubaccountsApi->view_subaccounts: #{e}"
end
```

#### Using the view_subaccounts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewSubaccounts>, Integer, Hash)> view_subaccounts_with_http_info(opts)

```ruby
begin
  # View Subaccounts
  data, status_code, headers = api_instance.view_subaccounts_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewSubaccounts>
rescue ClickSend::ApiError => e
  puts "Error when calling SubaccountsApi->view_subaccounts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewSubaccounts**](ViewSubaccounts.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

