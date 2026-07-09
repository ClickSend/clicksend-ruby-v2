# ClickSend::InternationalMessagingApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**agree_to_rules_and_regulation**](InternationalMessagingApi.md#agree_to_rules_and_regulation) | **POST** /v3/user-countries/agree | Agree to rules and regulation |
| [**get_countries_for_global_sending**](InternationalMessagingApi.md#get_countries_for_global_sending) | **GET** /v3/user-countries | Get Countries for Global Sending |
| [**list_countries**](InternationalMessagingApi.md#list_countries) | **GET** /v3/country-list | International Messaging |
| [**select_countries_for_global_sending**](InternationalMessagingApi.md#select_countries_for_global_sending) | **POST** /v3/user-countries | Select Countries for Global Sending |
| [**timezones**](InternationalMessagingApi.md#timezones) | **GET** /v3/timezones | Timezones |
| [**view_countries**](InternationalMessagingApi.md#view_countries) | **GET** /v3/countries | View Countries |


## agree_to_rules_and_regulation

> <AgreeToRulesAndRegulation> agree_to_rules_and_regulation

Agree to rules and regulation

_Update Country Rule_  To agree on rules and regulations of selected countries and confirm selection.  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | country_list_ids | number | true | none | Country list ID's |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::InternationalMessagingApi.new

begin
  # Agree to rules and regulation
  result = api_instance.agree_to_rules_and_regulation
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling InternationalMessagingApi->agree_to_rules_and_regulation: #{e}"
end
```

#### Using the agree_to_rules_and_regulation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AgreeToRulesAndRegulation>, Integer, Hash)> agree_to_rules_and_regulation_with_http_info

```ruby
begin
  # Agree to rules and regulation
  data, status_code, headers = api_instance.agree_to_rules_and_regulation_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AgreeToRulesAndRegulation>
rescue ClickSend::ApiError => e
  puts "Error when calling InternationalMessagingApi->agree_to_rules_and_regulation_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**AgreeToRulesAndRegulation**](AgreeToRulesAndRegulation.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_countries_for_global_sending

> <GetCountriesForGlobalSending> get_countries_for_global_sending

Get Countries for Global Sending

_Get Countries for global sending_  Get the list of selected countries.  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::InternationalMessagingApi.new

begin
  # Get Countries for Global Sending
  result = api_instance.get_countries_for_global_sending
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling InternationalMessagingApi->get_countries_for_global_sending: #{e}"
end
```

#### Using the get_countries_for_global_sending_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetCountriesForGlobalSending>, Integer, Hash)> get_countries_for_global_sending_with_http_info

```ruby
begin
  # Get Countries for Global Sending
  data, status_code, headers = api_instance.get_countries_for_global_sending_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetCountriesForGlobalSending>
rescue ClickSend::ApiError => e
  puts "Error when calling InternationalMessagingApi->get_countries_for_global_sending_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**GetCountriesForGlobalSending**](GetCountriesForGlobalSending.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_countries

> <ListCountries> list_countries

International Messaging

_List of countries_  List of countries with IDs that can be used in selecting countries for Global sending.  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::InternationalMessagingApi.new

begin
  # International Messaging
  result = api_instance.list_countries
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling InternationalMessagingApi->list_countries: #{e}"
end
```

#### Using the list_countries_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListCountries>, Integer, Hash)> list_countries_with_http_info

```ruby
begin
  # International Messaging
  data, status_code, headers = api_instance.list_countries_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListCountries>
rescue ClickSend::ApiError => e
  puts "Error when calling InternationalMessagingApi->list_countries_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ListCountries**](ListCountries.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## select_countries_for_global_sending

> <SelectCountriesForGlobalSending> select_countries_for_global_sending(opts)

Select Countries for Global Sending

_Select Countries_  Use this endpoint to select countries that you intend to send sms / mms to. To remove / unselect a country, just remove the country id from the array in the payload.  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | country_list_ids | number | true | none | Country list ID's |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::InternationalMessagingApi.new
opts = {
  select_countries_for_global_sending_request: ClickSend::SelectCountriesForGlobalSendingRequest.new # SelectCountriesForGlobalSendingRequest | 
}

begin
  # Select Countries for Global Sending
  result = api_instance.select_countries_for_global_sending(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling InternationalMessagingApi->select_countries_for_global_sending: #{e}"
end
```

#### Using the select_countries_for_global_sending_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SelectCountriesForGlobalSending>, Integer, Hash)> select_countries_for_global_sending_with_http_info(opts)

```ruby
begin
  # Select Countries for Global Sending
  data, status_code, headers = api_instance.select_countries_for_global_sending_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SelectCountriesForGlobalSending>
rescue ClickSend::ApiError => e
  puts "Error when calling InternationalMessagingApi->select_countries_for_global_sending_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **select_countries_for_global_sending_request** | [**SelectCountriesForGlobalSendingRequest**](SelectCountriesForGlobalSendingRequest.md) |  | [optional] |

### Return type

[**SelectCountriesForGlobalSending**](SelectCountriesForGlobalSending.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## timezones

> <Timezones> timezones(opts)

Timezones

_Get supported list of timezones._  Get supported list of timezones.  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | Page number | | limit | query | integer(int32) | false | Number of records per page |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::InternationalMessagingApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Timezones
  result = api_instance.timezones(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling InternationalMessagingApi->timezones: #{e}"
end
```

#### Using the timezones_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Timezones>, Integer, Hash)> timezones_with_http_info(opts)

```ruby
begin
  # Timezones
  data, status_code, headers = api_instance.timezones_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Timezones>
rescue ClickSend::ApiError => e
  puts "Error when calling InternationalMessagingApi->timezones_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**Timezones**](Timezones.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_countries

> <ViewCountries> view_countries

View Countries

_Get all country codes_  Get all countries   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #6BBD5B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint does not require authentication</span>  </div>

### Examples

```ruby
require 'time'
require 'clicksend'

api_instance = ClickSend::InternationalMessagingApi.new

begin
  # View Countries
  result = api_instance.view_countries
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling InternationalMessagingApi->view_countries: #{e}"
end
```

#### Using the view_countries_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewCountries>, Integer, Hash)> view_countries_with_http_info

```ruby
begin
  # View Countries
  data, status_code, headers = api_instance.view_countries_with_http_info
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewCountries>
rescue ClickSend::ApiError => e
  puts "Error when calling InternationalMessagingApi->view_countries_with_http_info: #{e}"
end
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**ViewCountries**](ViewCountries.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

