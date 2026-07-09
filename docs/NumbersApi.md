# ClickSend::NumbersApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**purchase_dedicated_number**](NumbersApi.md#purchase_dedicated_number) | **POST** /v3/numbers/buy/{dedicated_number} | Purchase Dedicated Number |
| [**register_numbers**](NumbersApi.md#register_numbers) | **POST** /v3/numbers/registrations/number-types/{number_type}/country/{country_code} | Register Numbers |
| [**view_available_numbers**](NumbersApi.md#view_available_numbers) | **GET** /v3/numbers/search/{country} | View Available Numbers |
| [**view_your_numbers**](NumbersApi.md#view_your_numbers) | **GET** /v3/numbers | View Your Numbers |


## purchase_dedicated_number

> <PurchaseDedicatedNumber> purchase_dedicated_number(dedicated_number, buy_number_request, opts)

Purchase Dedicated Number

_Buy dedicated number_  This endpoint allows you to purchase a dedicated phone number for messaging services. You can optionally include registration data for compliance purposes.  ### Request Body  | Field | Type | Required | Description | | --- | --- | --- | --- | | dedicated_number | string | true | Phone number to purchase | | type | string | true | Service type (sms, mms) | | registration_data | object | false | Registration data for compliance (AU SMS/MMS numbers only) |  #### Registration Data Fields (Optional)  | Field | Type | Required | Description | | --- | --- | --- | --- | | business_name | string | true | Name of the business (2 - 100 characters) | | business_address | string | true | Business address (5 - 150 characters) | | suburb | string | true | Suburb/City (2 - 50 characters) | | postcode | string | true | Postal code (2 - 20 characters) | | state | string | true | State/Province (2 - 50 characters) | | contact_name | string | true | Contact person name (2 - 100 characters) | | contact_number | string | true | Contact phone number (valid local or international phone number) | | country | string | true | Country code (ISO 3166-1 alpha-2) |   ### Path Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | dedicated_number | path | string | true | Phone number to purchase |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::NumbersApi.new
dedicated_number = '+614197651956' # String | Phone number to purchase
buy_number_request = ClickSend::BuyNumberRequest.new({dedicated_number: '+614197651956', type: 'sms'}) # BuyNumberRequest | 
opts = {
  content_type: 'application/json', # String | 
  type: 'sms' # String | 
}

begin
  # Purchase Dedicated Number
  result = api_instance.purchase_dedicated_number(dedicated_number, buy_number_request, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling NumbersApi->purchase_dedicated_number: #{e}"
end
```

#### Using the purchase_dedicated_number_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<PurchaseDedicatedNumber>, Integer, Hash)> purchase_dedicated_number_with_http_info(dedicated_number, buy_number_request, opts)

```ruby
begin
  # Purchase Dedicated Number
  data, status_code, headers = api_instance.purchase_dedicated_number_with_http_info(dedicated_number, buy_number_request, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <PurchaseDedicatedNumber>
rescue ClickSend::ApiError => e
  puts "Error when calling NumbersApi->purchase_dedicated_number_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dedicated_number** | **String** | Phone number to purchase |  |
| **buy_number_request** | [**BuyNumberRequest**](BuyNumberRequest.md) |  |  |
| **content_type** | **String** |  | [optional] |
| **type** | **String** |  | [optional] |

### Return type

[**PurchaseDedicatedNumber**](PurchaseDedicatedNumber.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## register_numbers

> <RegisterNumbers> register_numbers(number_type, country_code, opts)

Register Numbers

<div style=\"background-color: #e8f4ff; padding: 15px; border-radius: 4px; border-left: 4px solid #0066cc;\"> This endpoint is currently only available for <b>Canada 10DLC</b> number registration. </div>  Registers a number that requires additional verification information. This endpoint facilitates the registration process for numbers requiring special compliance documentation.  After submission, ClickSend's compliance team will review the registration and notify you of the approval status.  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses. <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::NumbersApi.new
number_type = '10dlc' # String | The type of number being registered
country_code = 'US, CA' # String | Two-character ISO country code
opts = {
  content_type: 'application/json', # String | 
  register_numbers_request: ClickSend::RegisterNumbersRequest.new({full_name: 'John Doe', company_name: 'ClickSend', email: 'john.doe@clicksend.com', website_url: 'https://clicksend.com', sample_message: 'Get 20% off on your next purchase! Visit our website for details.', primary_use_case: 'Marketing', company_number: '+1-800-555-0199', area_code: '416, 647, 905'}) # RegisterNumbersRequest | 
}

begin
  # Register Numbers
  result = api_instance.register_numbers(number_type, country_code, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling NumbersApi->register_numbers: #{e}"
end
```

#### Using the register_numbers_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RegisterNumbers>, Integer, Hash)> register_numbers_with_http_info(number_type, country_code, opts)

```ruby
begin
  # Register Numbers
  data, status_code, headers = api_instance.register_numbers_with_http_info(number_type, country_code, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RegisterNumbers>
rescue ClickSend::ApiError => e
  puts "Error when calling NumbersApi->register_numbers_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **number_type** | **String** | The type of number being registered |  |
| **country_code** | **String** | Two-character ISO country code |  |
| **content_type** | **String** |  | [optional] |
| **register_numbers_request** | [**RegisterNumbersRequest**](RegisterNumbersRequest.md) |  | [optional] |

### Return type

[**RegisterNumbers**](RegisterNumbers.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## view_available_numbers

> <ViewAvailableNumbers> view_available_numbers(country, opts)

View Available Numbers

_Get all dedicated numbers by country_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | country | path | string | true | Country code to search | | search | query | string | false | Your search pattern or query. | | search_type | query | integer(int32) | false | Your strategy for searching, 0 = starts with, 1 = anywhere, 2 = ends with. | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::NumbersApi.new
country = 'country_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Available Numbers
  result = api_instance.view_available_numbers(country, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling NumbersApi->view_available_numbers: #{e}"
end
```

#### Using the view_available_numbers_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewAvailableNumbers>, Integer, Hash)> view_available_numbers_with_http_info(country, opts)

```ruby
begin
  # View Available Numbers
  data, status_code, headers = api_instance.view_available_numbers_with_http_info(country, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewAvailableNumbers>
rescue ClickSend::ApiError => e
  puts "Error when calling NumbersApi->view_available_numbers_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **country** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewAvailableNumbers**](ViewAvailableNumbers.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_your_numbers

> <ViewYourNumbers> view_your_numbers(opts)

View Your Numbers

_Get all available dedicated numbers_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) | | q | query | string | false | Filter numbers based on multiple criteria. The query string should be formatted as key-value pairs separated by commas. Available filter keys: `type`, `number_type`, `country` | | q2 | query | string | false | Filter numbers based on multiple criteria. The query string should be formatted as key-value pairs separated by commas. Available filter keys: `type` | | excluding_number_type | query | string | false | Exclude specific number types from the results. Available number types: `shortcode`, `tollfree`, `10DLC` | | exclude_10dlc_campaign | query | boolean | false | When set to true, excludes all numbers that are associated with 10DLC campaigns |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::NumbersApi.new
opts = {
  content_type: 'application/json', # String | 
  page: 1, # Integer | Page number
  limit: 100, # Integer | Number of records per page
  q: 'type:sms,number_type:longcode,country:AU', # String | Filter numbers based on multiple criteria. The query string should be formatted as key-value pairs separated by commas. Available filter keys: - `type`: Message type (e.g., `SMS`, `MMS`) - `number_type`: Number classification (e.g., `longcode`, `shortcode`, `tollfree`, `10DLC`) - `country`: Two-letter country code (e.g., `AU`, `US`) 
  q2: 'type:mms', # String | 
  excluding_number_type: '10DLC', # String | Exclude specific number types from the results. Available number types: - `shortcode` - `tollfree` - `10DLC` 
  exclude_10dlc_campaign: true # Boolean | When set to true, excludes all numbers that are associated with 10DLC campaigns
}

begin
  # View Your Numbers
  result = api_instance.view_your_numbers(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling NumbersApi->view_your_numbers: #{e}"
end
```

#### Using the view_your_numbers_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewYourNumbers>, Integer, Hash)> view_your_numbers_with_http_info(opts)

```ruby
begin
  # View Your Numbers
  data, status_code, headers = api_instance.view_your_numbers_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewYourNumbers>
rescue ClickSend::ApiError => e
  puts "Error when calling NumbersApi->view_your_numbers_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **page** | **Integer** | Page number | [optional][default to 1] |
| **limit** | **Integer** | Number of records per page | [optional][default to 15] |
| **q** | **String** | Filter numbers based on multiple criteria. The query string should be formatted as key-value pairs separated by commas. Available filter keys: - &#x60;type&#x60;: Message type (e.g., &#x60;SMS&#x60;, &#x60;MMS&#x60;) - &#x60;number_type&#x60;: Number classification (e.g., &#x60;longcode&#x60;, &#x60;shortcode&#x60;, &#x60;tollfree&#x60;, &#x60;10DLC&#x60;) - &#x60;country&#x60;: Two-letter country code (e.g., &#x60;AU&#x60;, &#x60;US&#x60;)  | [optional] |
| **q2** | **String** |  | [optional] |
| **excluding_number_type** | **String** | Exclude specific number types from the results. Available number types: - &#x60;shortcode&#x60; - &#x60;tollfree&#x60; - &#x60;10DLC&#x60;  | [optional] |
| **exclude_10dlc_campaign** | **Boolean** | When set to true, excludes all numbers that are associated with 10DLC campaigns | [optional][default to false] |

### Return type

[**ViewYourNumbers**](ViewYourNumbers.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

