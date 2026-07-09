# ClickSend::UrlShorteningApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**short_url_get_statistics**](UrlShorteningApi.md#short_url_get_statistics) | **GET** /v3/short-url/statistics/{source}/{source_id} | Get Statistics |
| [**short_url_get_tracking**](UrlShorteningApi.md#short_url_get_tracking) | **GET** /v3/short-url/tracking/{long_url_id} | Get Tracking |


## short_url_get_statistics

> <GetStatistics> short_url_get_statistics(source, source_id, opts)

Get Statistics

Use this endpoint to get the aggregated statistics for a shortened URL. This allows you to track the total number of clicks on the link. You can gather details such as the device type and where it was opened from as well.

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

api_instance = ClickSend::UrlShorteningApi.new
source = 'quick_sms' # String | Source of the request.
source_id = 'source_id_example' # String | ID of the source (e.g. message ID).
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Get Statistics
  result = api_instance.short_url_get_statistics(source, source_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling UrlShorteningApi->short_url_get_statistics: #{e}"
end
```

#### Using the short_url_get_statistics_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetStatistics>, Integer, Hash)> short_url_get_statistics_with_http_info(source, source_id, opts)

```ruby
begin
  # Get Statistics
  data, status_code, headers = api_instance.short_url_get_statistics_with_http_info(source, source_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetStatistics>
rescue ClickSend::ApiError => e
  puts "Error when calling UrlShorteningApi->short_url_get_statistics_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **source** | **String** | Source of the request. |  |
| **source_id** | **String** | ID of the source (e.g. message ID). |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**GetStatistics**](GetStatistics.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## short_url_get_tracking

> <GetTracking> short_url_get_tracking(long_url_id, opts)

Get Tracking

Use this endpoint to track how individual recipients interact with the link.  It returns data from the most recent click, including statistics such as how many times they’ve visited the link and when it was last opened. To use this endpoint, reference the _long_url_id_ provided in the [GET /short-url/statistics](/messaging/url-shortening/other/short-url-get-statistics) endpoint.

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

api_instance = ClickSend::UrlShorteningApi.new
long_url_id = 'long_url_id_example' # String | ID of the long URL (uniquely defined by the source, source ID, and long URL). Obtained from the GET statistics endpoint.
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Get Tracking
  result = api_instance.short_url_get_tracking(long_url_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling UrlShorteningApi->short_url_get_tracking: #{e}"
end
```

#### Using the short_url_get_tracking_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetTracking>, Integer, Hash)> short_url_get_tracking_with_http_info(long_url_id, opts)

```ruby
begin
  # Get Tracking
  data, status_code, headers = api_instance.short_url_get_tracking_with_http_info(long_url_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetTracking>
rescue ClickSend::ApiError => e
  puts "Error when calling UrlShorteningApi->short_url_get_tracking_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **long_url_id** | **String** | ID of the long URL (uniquely defined by the source, source ID, and long URL). Obtained from the GET statistics endpoint. |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**GetTracking**](GetTracking.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

