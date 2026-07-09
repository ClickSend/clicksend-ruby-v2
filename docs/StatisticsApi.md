# ClickSend::StatisticsApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**view_sms_statistics**](StatisticsApi.md#view_sms_statistics) | **GET** /v3/statistics/sms | View SMS Statistics |
| [**view_voice_statistics**](StatisticsApi.md#view_voice_statistics) | **GET** /v3/statistics/voice | View Voice Statistics |


## view_sms_statistics

> <ViewSmsStatistics> view_sms_statistics(opts)

View SMS Statistics

_Get sms statistics_   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::StatisticsApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View SMS Statistics
  result = api_instance.view_sms_statistics(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling StatisticsApi->view_sms_statistics: #{e}"
end
```

#### Using the view_sms_statistics_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewSmsStatistics>, Integer, Hash)> view_sms_statistics_with_http_info(opts)

```ruby
begin
  # View SMS Statistics
  data, status_code, headers = api_instance.view_sms_statistics_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewSmsStatistics>
rescue ClickSend::ApiError => e
  puts "Error when calling StatisticsApi->view_sms_statistics_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewSmsStatistics**](ViewSmsStatistics.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_voice_statistics

> <ViewVoiceStatistics> view_voice_statistics(opts)

View Voice Statistics

_Get voice statistics_  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::StatisticsApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Voice Statistics
  result = api_instance.view_voice_statistics(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling StatisticsApi->view_voice_statistics: #{e}"
end
```

#### Using the view_voice_statistics_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewVoiceStatistics>, Integer, Hash)> view_voice_statistics_with_http_info(opts)

```ruby
begin
  # View Voice Statistics
  data, status_code, headers = api_instance.view_voice_statistics_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewVoiceStatistics>
rescue ClickSend::ApiError => e
  puts "Error when calling StatisticsApi->view_voice_statistics_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewVoiceStatistics**](ViewVoiceStatistics.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

