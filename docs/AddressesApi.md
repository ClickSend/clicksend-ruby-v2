# ClickSend::AddressesApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_return_address**](AddressesApi.md#create_return_address) | **POST** /v3/post/return-addresses | Create Return Address |
| [**delete_return_address**](AddressesApi.md#delete_return_address) | **DELETE** /v3/post/return-addresses/{return_address_id} | Delete Return Address |
| [**update_return_address**](AddressesApi.md#update_return_address) | **PUT** /v3/post/return-addresses/{return_address_id} | Update Return Address |
| [**view_specific_return_address**](AddressesApi.md#view_specific_return_address) | **GET** /v3/post/return-addresses/{return_address_id} | View Specific Return Address |
| [**view_your_return_addresses**](AddressesApi.md#view_your_return_addresses) | **GET** /v3/post/return-addresses | View Your Return Addresses |


## create_return_address

> <CreateReturnAddress> create_return_address(opts)

Create Return Address

_Create post return address_  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | address_name | string | true | none | Your address name. | | address_line_1 | string | true | none | Your address line 1 | | address_city | string | true | none | Your city | | address_postal_code | string | true | none | Your postal code | | address_country | string | true | none | Your country | | address_line_2 | string | false | none | Your address line 2 | | address_state | string | false | none | Your state |    Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.    <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::AddressesApi.new
opts = {
  content_type: 'application/json', # String | 
  create_return_address_request: ClickSend::CreateReturnAddressRequest.new # CreateReturnAddressRequest | 
}

begin
  # Create Return Address
  result = api_instance.create_return_address(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling AddressesApi->create_return_address: #{e}"
end
```

#### Using the create_return_address_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateReturnAddress>, Integer, Hash)> create_return_address_with_http_info(opts)

```ruby
begin
  # Create Return Address
  data, status_code, headers = api_instance.create_return_address_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateReturnAddress>
rescue ClickSend::ApiError => e
  puts "Error when calling AddressesApi->create_return_address_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **create_return_address_request** | [**CreateReturnAddressRequest**](CreateReturnAddressRequest.md) |  | [optional] |

### Return type

[**CreateReturnAddress**](CreateReturnAddress.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_return_address

> <DeleteReturnAddress> delete_return_address(return_address_id, opts)

Delete Return Address

_Delete specific post return address_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | return_address_id | path | integer(int32) | true | Return address ID |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::AddressesApi.new
return_address_id = 'return_address_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Delete Return Address
  result = api_instance.delete_return_address(return_address_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling AddressesApi->delete_return_address: #{e}"
end
```

#### Using the delete_return_address_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteReturnAddress>, Integer, Hash)> delete_return_address_with_http_info(return_address_id, opts)

```ruby
begin
  # Delete Return Address
  data, status_code, headers = api_instance.delete_return_address_with_http_info(return_address_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteReturnAddress>
rescue ClickSend::ApiError => e
  puts "Error when calling AddressesApi->delete_return_address_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **return_address_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**DeleteReturnAddress**](DeleteReturnAddress.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_return_address

> <UpdateReturnAddress> update_return_address(return_address_id, opts)

Update Return Address

_Update post return address_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | return_address_id | path | integer(int32) | true | Return address ID |  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | address_name | string | true | none | Your address name. | | address_line_1 | string | true | none | Your address line 1 | | address_city | string | true | none | Your city | | address_postal_code | string | true | none | Your postal code | | address_country | string | true | none | Your country | | address_line_2 | string | false | none | Your address line 2 | | address_state | string | false | none | Your state |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::AddressesApi.new
return_address_id = 'return_address_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  update_return_address_request: ClickSend::UpdateReturnAddressRequest.new # UpdateReturnAddressRequest | 
}

begin
  # Update Return Address
  result = api_instance.update_return_address(return_address_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling AddressesApi->update_return_address: #{e}"
end
```

#### Using the update_return_address_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateReturnAddress>, Integer, Hash)> update_return_address_with_http_info(return_address_id, opts)

```ruby
begin
  # Update Return Address
  data, status_code, headers = api_instance.update_return_address_with_http_info(return_address_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateReturnAddress>
rescue ClickSend::ApiError => e
  puts "Error when calling AddressesApi->update_return_address_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **return_address_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **update_return_address_request** | [**UpdateReturnAddressRequest**](UpdateReturnAddressRequest.md) |  | [optional] |

### Return type

[**UpdateReturnAddress**](UpdateReturnAddress.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## view_specific_return_address

> <ViewSpecificReturnAddress> view_specific_return_address(return_address_id, opts)

View Specific Return Address

_Get specific post return address_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | return_address_id | path | integer(int32) | true | Return address ID |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::AddressesApi.new
return_address_id = 'return_address_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Specific Return Address
  result = api_instance.view_specific_return_address(return_address_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling AddressesApi->view_specific_return_address: #{e}"
end
```

#### Using the view_specific_return_address_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewSpecificReturnAddress>, Integer, Hash)> view_specific_return_address_with_http_info(return_address_id, opts)

```ruby
begin
  # View Specific Return Address
  data, status_code, headers = api_instance.view_specific_return_address_with_http_info(return_address_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewSpecificReturnAddress>
rescue ClickSend::ApiError => e
  puts "Error when calling AddressesApi->view_specific_return_address_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **return_address_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewSpecificReturnAddress**](ViewSpecificReturnAddress.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_your_return_addresses

> <ViewYourReturnAddresses> view_your_return_addresses(opts)

View Your Return Addresses

_Get list of post return addresses_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::AddressesApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Your Return Addresses
  result = api_instance.view_your_return_addresses(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling AddressesApi->view_your_return_addresses: #{e}"
end
```

#### Using the view_your_return_addresses_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewYourReturnAddresses>, Integer, Hash)> view_your_return_addresses_with_http_info(opts)

```ruby
begin
  # View Your Return Addresses
  data, status_code, headers = api_instance.view_your_return_addresses_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewYourReturnAddresses>
rescue ClickSend::ApiError => e
  puts "Error when calling AddressesApi->view_your_return_addresses_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewYourReturnAddresses**](ViewYourReturnAddresses.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

