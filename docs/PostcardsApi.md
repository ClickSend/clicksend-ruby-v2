# ClickSend::PostcardsApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**calculate_postcard_price**](PostcardsApi.md#calculate_postcard_price) | **POST** /v3/post/postcards/price | Calculate Postcard Price |
| [**cancel_scheduled_postcard**](PostcardsApi.md#cancel_scheduled_postcard) | **PUT** /v3/post/postcards/{message_id}/cancel | Cancel Scheduled Postcard |
| [**export_postcard_history**](PostcardsApi.md#export_postcard_history) | **GET** /v3/post/postcards/history/export | Export Postcard History |
| [**send_postcard**](PostcardsApi.md#send_postcard) | **POST** /v3/post/postcards/send | Send Postcard |
| [**view_postcard_history**](PostcardsApi.md#view_postcard_history) | **GET** /v3/post/postcards/history | View Postcard History |


## calculate_postcard_price

> <CalculatePostcardPrice> calculate_postcard_price(opts)

Calculate Postcard Price

_Calculate price for sending one or more postcards_  For `file_urls` field. You can attach at least 1 and max of 2 PDF file urls.  - Supply a single pdf with 2 pages (front and back) - Supply 2 urls to seperate PDFs       ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | file_urls | \\[string\\] | true | none | Postcard file URLs | | address_name | string | true | none | Name of address | | address_line_1 | string | true | none | First line of address | | address_line_2 | string | true | none | Second line of address | | address_city | string | true | none | City | | address_state | string | true | none | State | | address_postal_code | string | true | none | Postal code | | address_country | string | true | none | Country | | return_address_id | integer(int32) | true | none | ID of return address to use | | schedule | integer(int32) | false | none | When to send letter (0/null=now) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::PostcardsApi.new
opts = {
  content_type: 'application/json', # String | 
  send_postcard_request: ClickSend::SendPostcardRequest.new # SendPostcardRequest | 
}

begin
  # Calculate Postcard Price
  result = api_instance.calculate_postcard_price(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling PostcardsApi->calculate_postcard_price: #{e}"
end
```

#### Using the calculate_postcard_price_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalculatePostcardPrice>, Integer, Hash)> calculate_postcard_price_with_http_info(opts)

```ruby
begin
  # Calculate Postcard Price
  data, status_code, headers = api_instance.calculate_postcard_price_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalculatePostcardPrice>
rescue ClickSend::ApiError => e
  puts "Error when calling PostcardsApi->calculate_postcard_price_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **send_postcard_request** | [**SendPostcardRequest**](SendPostcardRequest.md) |  | [optional] |

### Return type

[**CalculatePostcardPrice**](CalculatePostcardPrice.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## cancel_scheduled_postcard

> <CancelScheduledPostcard> cancel_scheduled_postcard(message_id)

Cancel Scheduled Postcard

_Cancel scheduled postcard_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | message_id | query | string | true | Message ID of the scheduled postcard that is to be cancelled. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

### Examples

```ruby
require 'time'
require 'clicksend'

api_instance = ClickSend::PostcardsApi.new
message_id = 'message_id_example' # String | 

begin
  # Cancel Scheduled Postcard
  result = api_instance.cancel_scheduled_postcard(message_id)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling PostcardsApi->cancel_scheduled_postcard: #{e}"
end
```

#### Using the cancel_scheduled_postcard_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CancelScheduledPostcard>, Integer, Hash)> cancel_scheduled_postcard_with_http_info(message_id)

```ruby
begin
  # Cancel Scheduled Postcard
  data, status_code, headers = api_instance.cancel_scheduled_postcard_with_http_info(message_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CancelScheduledPostcard>
rescue ClickSend::ApiError => e
  puts "Error when calling PostcardsApi->cancel_scheduled_postcard_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** |  |  |

### Return type

[**CancelScheduledPostcard**](CancelScheduledPostcard.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## export_postcard_history

> <ExportPostcardHistory> export_postcard_history(opts)

Export Postcard History

_Export postcard history to a CSV file_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | filename | query | string | true | Filename to export to |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::PostcardsApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Export Postcard History
  result = api_instance.export_postcard_history(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling PostcardsApi->export_postcard_history: #{e}"
end
```

#### Using the export_postcard_history_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ExportPostcardHistory>, Integer, Hash)> export_postcard_history_with_http_info(opts)

```ruby
begin
  # Export Postcard History
  data, status_code, headers = api_instance.export_postcard_history_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ExportPostcardHistory>
rescue ClickSend::ApiError => e
  puts "Error when calling PostcardsApi->export_postcard_history_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ExportPostcardHistory**](ExportPostcardHistory.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## send_postcard

> <SendPostcard> send_postcard(opts)

Send Postcard

_Send one or more postcards_  ### **Supported File Types**  We support PDF, docx, doc, jpg, gif, png, and bmp. Contact us to add support for any other file type. If you're using docx, doc, jpg, gif, png, or bmp files, you'll need to convert the file first using our uploads endpoint with the querystring parameter ?convert=postcard. e.g. POST /uploads?convert=postcard. This will return a URL to the converted pdf file that can be used in the /post/postcards/send endpoint.  ### **Postcard Specification Guide**  Follow our [Postcard specification guide](https://help.clicksend.com/article/ysyql7bsr1-postcard-template) to ensure correct sending and postcard template information.  ### **Postcard File Options**  ### Use existing URL  With this option, you can use an existing URL to a `pdf` document. For example, you might generate the `pdf` on your server.  When using an existing url make sure that it is publicly accessible as it will not work if it is private.  For `file_urls` field. You can attach at least 1 and max of 2 PDF file urls.  - Supply a single pdf with 2 pages (front and back) - Supply 2 urls to seperate PDFs       ### Upload File to Our Server  With this option, you can use the [/uploads](/#upload-media-file) endpoint to upload the document. The `/uploads` endpoint returns a URL that can be used in the `/post/postcards/send` endpoint.  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | file_urls | \\[string\\] | true | none | Postcard file URLs | | address_name | string | true | none | Name of address | | address_line_1 | string | true | none | First line of address | | address_line_2 | string | true | none | Second line of address | | address_city | string | true | none | City | | address_state | string | true | none | State | | address_postal_code | string | true | none | Postal code | | address_country | string | true | none | Country | | return_address_id | integer(int32) | true | none | ID of return address to use | | schedule | integer(int32) | false | none | When to send letter (0/null=now) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::PostcardsApi.new
opts = {
  content_type: 'application/json', # String | 
  send_postcard_request: ClickSend::SendPostcardRequest.new # SendPostcardRequest | 
}

begin
  # Send Postcard
  result = api_instance.send_postcard(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling PostcardsApi->send_postcard: #{e}"
end
```

#### Using the send_postcard_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendPostcard>, Integer, Hash)> send_postcard_with_http_info(opts)

```ruby
begin
  # Send Postcard
  data, status_code, headers = api_instance.send_postcard_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendPostcard>
rescue ClickSend::ApiError => e
  puts "Error when calling PostcardsApi->send_postcard_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **send_postcard_request** | [**SendPostcardRequest**](SendPostcardRequest.md) |  | [optional] |

### Return type

[**SendPostcard**](SendPostcard.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## view_postcard_history

> <ViewPostcardHistory> view_postcard_history(opts)

View Postcard History

_Retrieve the history of postcards sent or scheduled_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::PostcardsApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Postcard History
  result = api_instance.view_postcard_history(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling PostcardsApi->view_postcard_history: #{e}"
end
```

#### Using the view_postcard_history_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewPostcardHistory>, Integer, Hash)> view_postcard_history_with_http_info(opts)

```ruby
begin
  # View Postcard History
  data, status_code, headers = api_instance.view_postcard_history_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewPostcardHistory>
rescue ClickSend::ApiError => e
  puts "Error when calling PostcardsApi->view_postcard_history_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewPostcardHistory**](ViewPostcardHistory.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

