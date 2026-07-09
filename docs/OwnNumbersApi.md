# ClickSend::OwnNumbersApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**delete_own_number**](OwnNumbersApi.md#delete_own_number) | **DELETE** /v3/own-numbers/{own_number_id} | Delete Own Number |
| [**get_own_number_detail**](OwnNumbersApi.md#get_own_number_detail) | **GET** /v3/own-numbers/{own_number_id} | Get Own Number Detail |
| [**list_own_numbers**](OwnNumbersApi.md#list_own_numbers) | **GET** /v3/own-numbers | List Own Numbers |
| [**request_own_number_verification_otp**](OwnNumbersApi.md#request_own_number_verification_otp) | **POST** /v3/own-numbers/verifications | Request Own Number Verification OTP |
| [**update_own_number**](OwnNumbersApi.md#update_own_number) | **PATCH** /v3/own-numbers/{own_number_id} | Update Own Number |
| [**verify_own_number_otp**](OwnNumbersApi.md#verify_own_number_otp) | **POST** /v3/own-numbers/verifications/{verification_id}/verify | Verify Own Number OTP |


## delete_own_number

> <OwnNumber> delete_own_number(own_number_id, opts)

Delete Own Number

_Delete a specific own numbers._  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | own_number_id | path | uuid | true | ID of the own number |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  This endpoint requires authentication, [more info...](/#authentication)

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

api_instance = ClickSend::OwnNumbersApi.new
own_number_id = 'own_number_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Delete Own Number
  result = api_instance.delete_own_number(own_number_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling OwnNumbersApi->delete_own_number: #{e}"
end
```

#### Using the delete_own_number_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OwnNumber>, Integer, Hash)> delete_own_number_with_http_info(own_number_id, opts)

```ruby
begin
  # Delete Own Number
  data, status_code, headers = api_instance.delete_own_number_with_http_info(own_number_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OwnNumber>
rescue ClickSend::ApiError => e
  puts "Error when calling OwnNumbersApi->delete_own_number_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **own_number_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**OwnNumber**](OwnNumber.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_own_number_detail

> <OwnNumber> get_own_number_detail(own_number_id, opts)

Get Own Number Detail

_Get a specific own numbers._  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | own_number_id | path | uuid | true | ID of the own number |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  This endpoint requires authentication, [more info...](/#authentication)

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

api_instance = ClickSend::OwnNumbersApi.new
own_number_id = 'own_number_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Get Own Number Detail
  result = api_instance.get_own_number_detail(own_number_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling OwnNumbersApi->get_own_number_detail: #{e}"
end
```

#### Using the get_own_number_detail_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OwnNumber>, Integer, Hash)> get_own_number_detail_with_http_info(own_number_id, opts)

```ruby
begin
  # Get Own Number Detail
  data, status_code, headers = api_instance.get_own_number_detail_with_http_info(own_number_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OwnNumber>
rescue ClickSend::ApiError => e
  puts "Error when calling OwnNumbersApi->get_own_number_detail_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **own_number_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**OwnNumber**](OwnNumber.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_own_numbers

> <ListOwnNumbers> list_own_numbers(opts)

List Own Numbers

_List own numbers._  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | offset | query | uuid | false | Page(offset) to be used for pagination. Example: `offset=f99872cc-11a6-48ba-a9f2-bcfb6dd1e3d4#8fa5ebc2-777b-45db-a448-ec76a40d4384` | | page_size | query | integer | false | Number of records per page. Default: 10. Range \\[1..500\\] | | filter\\[status\\]\\[\\] | query | string | false | Filter by statuses. Value must be in enum \\[`PENDING`, `APPROVED`, `REJECTED`\\]. For example: `filter[status][0]=PENDING&filter[status][1]=APPROVED` . | | sort_by | query | string | false | Sort by parameter. Default: `created_timestamp` | | sort_direction | query | string | false | Direction of sorting. Default: `asc`. Value must be in enum \\[`asc`, `desc`\\]. |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   This endpoint requires authentication, [more info...](/#authentication)

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

api_instance = ClickSend::OwnNumbersApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # List Own Numbers
  result = api_instance.list_own_numbers(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling OwnNumbersApi->list_own_numbers: #{e}"
end
```

#### Using the list_own_numbers_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListOwnNumbers>, Integer, Hash)> list_own_numbers_with_http_info(opts)

```ruby
begin
  # List Own Numbers
  data, status_code, headers = api_instance.list_own_numbers_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListOwnNumbers>
rescue ClickSend::ApiError => e
  puts "Error when calling OwnNumbersApi->list_own_numbers_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ListOwnNumbers**](ListOwnNumbers.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## request_own_number_verification_otp

> <RequestOwnNumberVerificationOtp> request_own_number_verification_otp(opts)

Request Own Number Verification OTP

_Request to generate own number verification OTP_  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | label | string | false | none | Custom label for phone number. Length must be between 1 - 200 characters. | | phone_number | string | true | none | Phone number. | | country | string | false | none | Country code. |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  This endpoint requires authentication, [more info...](/#authentication)

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

api_instance = ClickSend::OwnNumbersApi.new
opts = {
  content_type: 'application/json', # String | 
  request_own_number_verification_otp_request: ClickSend::RequestOwnNumberVerificationOtpRequest.new # RequestOwnNumberVerificationOtpRequest | 
}

begin
  # Request Own Number Verification OTP
  result = api_instance.request_own_number_verification_otp(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling OwnNumbersApi->request_own_number_verification_otp: #{e}"
end
```

#### Using the request_own_number_verification_otp_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RequestOwnNumberVerificationOtp>, Integer, Hash)> request_own_number_verification_otp_with_http_info(opts)

```ruby
begin
  # Request Own Number Verification OTP
  data, status_code, headers = api_instance.request_own_number_verification_otp_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RequestOwnNumberVerificationOtp>
rescue ClickSend::ApiError => e
  puts "Error when calling OwnNumbersApi->request_own_number_verification_otp_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **request_own_number_verification_otp_request** | [**RequestOwnNumberVerificationOtpRequest**](RequestOwnNumberVerificationOtpRequest.md) |  | [optional] |

### Return type

[**RequestOwnNumberVerificationOtp**](RequestOwnNumberVerificationOtp.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_own_number

> <OwnNumber> update_own_number(own_number_id)

Update Own Number

_Update details of a specific own numbers._  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | own_number_id | path | uuid | true | ID of the own number |  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | label | string | false | none | Custom label for phone number. Length must be between 1 - 200 characters. |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  This endpoint requires authentication, [more info...](/#authentication)

### Examples

```ruby
require 'time'
require 'clicksend'

api_instance = ClickSend::OwnNumbersApi.new
own_number_id = 'own_number_id_example' # String | 

begin
  # Update Own Number
  result = api_instance.update_own_number(own_number_id)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling OwnNumbersApi->update_own_number: #{e}"
end
```

#### Using the update_own_number_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<OwnNumber>, Integer, Hash)> update_own_number_with_http_info(own_number_id)

```ruby
begin
  # Update Own Number
  data, status_code, headers = api_instance.update_own_number_with_http_info(own_number_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <OwnNumber>
rescue ClickSend::ApiError => e
  puts "Error when calling OwnNumbersApi->update_own_number_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **own_number_id** | **String** |  |  |

### Return type

[**OwnNumber**](OwnNumber.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## verify_own_number_otp

> <VerifyOwnNumberOtp> verify_own_number_otp(verification_id, opts)

Verify Own Number OTP

_Request to verify an OTP for Own Number verification_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | verification_id | path | uuid | true | ID of the Own Number verification |  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | code | string | true | none | OTP code. Length must be 6 characters | | phone_number | string | true | none | Phone number. | | country | string | false | none | Country code. |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  This endpoint requires authentication, [more info...](/#authentication)

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

api_instance = ClickSend::OwnNumbersApi.new
verification_id = 'verification_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  verify_own_number_otp_request: ClickSend::VerifyOwnNumberOtpRequest.new # VerifyOwnNumberOtpRequest | 
}

begin
  # Verify Own Number OTP
  result = api_instance.verify_own_number_otp(verification_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling OwnNumbersApi->verify_own_number_otp: #{e}"
end
```

#### Using the verify_own_number_otp_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<VerifyOwnNumberOtp>, Integer, Hash)> verify_own_number_otp_with_http_info(verification_id, opts)

```ruby
begin
  # Verify Own Number OTP
  data, status_code, headers = api_instance.verify_own_number_otp_with_http_info(verification_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <VerifyOwnNumberOtp>
rescue ClickSend::ApiError => e
  puts "Error when calling OwnNumbersApi->verify_own_number_otp_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **verification_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **verify_own_number_otp_request** | [**VerifyOwnNumberOtpRequest**](VerifyOwnNumberOtpRequest.md) |  | [optional] |

### Return type

[**VerifyOwnNumberOtp**](VerifyOwnNumberOtp.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

