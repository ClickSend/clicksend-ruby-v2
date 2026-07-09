# ClickSend::ManagementApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**view_account_details**](ManagementApi.md#view_account_details) | **GET** /v3/account | View Account Details |
| [**view_account_usage**](ManagementApi.md#view_account_usage) | **GET** /v3/account/usage/{year}/{month}/subaccount | View Account Usage |


## view_account_details

> <ViewAccountDetails> view_account_details(opts)

View Account Details

_Get account information_  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/#pagination\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::ManagementApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Account Details
  result = api_instance.view_account_details(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ManagementApi->view_account_details: #{e}"
end
```

#### Using the view_account_details_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewAccountDetails>, Integer, Hash)> view_account_details_with_http_info(opts)

```ruby
begin
  # View Account Details
  data, status_code, headers = api_instance.view_account_details_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewAccountDetails>
rescue ClickSend::ApiError => e
  puts "Error when calling ManagementApi->view_account_details_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewAccountDetails**](ViewAccountDetails.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_account_usage

> <ViewAccountUsage> view_account_usage(year, month, opts)

View Account Usage

_Get account usage_  | **Name** | **Type** | **Required** | **Restrictions** | **Description** | | --- | --- | --- | --- | --- | | year | string | true | none | Your account usage year. Example: 2019 | | month | string | true | none | Your account usage month. Example: 4 |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/#pagination\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::ManagementApi.new
year = 'year_example' # String | 
month = 'month_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Account Usage
  result = api_instance.view_account_usage(year, month, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ManagementApi->view_account_usage: #{e}"
end
```

#### Using the view_account_usage_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewAccountUsage>, Integer, Hash)> view_account_usage_with_http_info(year, month, opts)

```ruby
begin
  # View Account Usage
  data, status_code, headers = api_instance.view_account_usage_with_http_info(year, month, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewAccountUsage>
rescue ClickSend::ApiError => e
  puts "Error when calling ManagementApi->view_account_usage_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **year** | **String** |  |  |
| **month** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewAccountUsage**](ViewAccountUsage.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

