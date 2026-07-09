# ClickSend::MmsApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**calculate_mms_price**](MmsApi.md#calculate_mms_price) | **POST** /v3/mms/price | Calculate MMS Price |
| [**export_mms_history**](MmsApi.md#export_mms_history) | **GET** /v3/mms/history/export | Export MMS History |
| [**send_mms**](MmsApi.md#send_mms) | **POST** /v3/mms/send | Send MMS |
| [**view_mms_history**](MmsApi.md#view_mms_history) | **GET** /v3/mms/history | View MMS History |


## calculate_mms_price

> <CalculateMmsPrice> calculate_mms_price(opts)

Calculate MMS Price

_Get Price for MMS sent_  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | media_file | string | true | none | Media file you want to send | | to | string | true | none | Recipient phone number in [E.164](https://en.wikipedia.org/wiki/E.164) format | | body | string | true | none | Your message | | subject | string | true | none | Subject line (max 20 characters) | | from | string | true | [yes](http://help.clicksend.com/SMS/what-is-a-sender-id-or-sender-number) | Your sender id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::MmsApi.new
opts = {
  content_type: 'application/json', # String | 
  calculate_mms_price_request: ClickSend::CalculateMmsPriceRequest.new # CalculateMmsPriceRequest | 
}

begin
  # Calculate MMS Price
  result = api_instance.calculate_mms_price(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling MmsApi->calculate_mms_price: #{e}"
end
```

#### Using the calculate_mms_price_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalculateMmsPrice>, Integer, Hash)> calculate_mms_price_with_http_info(opts)

```ruby
begin
  # Calculate MMS Price
  data, status_code, headers = api_instance.calculate_mms_price_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalculateMmsPrice>
rescue ClickSend::ApiError => e
  puts "Error when calling MmsApi->calculate_mms_price_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **calculate_mms_price_request** | [**CalculateMmsPriceRequest**](CalculateMmsPriceRequest.md) |  | [optional] |

### Return type

[**CalculateMmsPrice**](CalculateMmsPrice.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## export_mms_history

> <ExportMmsHistory> export_mms_history(opts)

Export MMS History

_Export all mms history_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | filename | query | string | true | Filename to download history as |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::MmsApi.new
opts = {
  content_type: 'application/json', # String | 
  filename: 'MMS_history.csv', # String | 
  q: 'q_example', # String | 
  order_by: 'date_added:desc', # String | 
  date_from: 'date_from_example', # String | 
  date_to: 'date_to_example', # String | 
  limit: 50000 # Integer | 
}

begin
  # Export MMS History
  result = api_instance.export_mms_history(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling MmsApi->export_mms_history: #{e}"
end
```

#### Using the export_mms_history_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ExportMmsHistory>, Integer, Hash)> export_mms_history_with_http_info(opts)

```ruby
begin
  # Export MMS History
  data, status_code, headers = api_instance.export_mms_history_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ExportMmsHistory>
rescue ClickSend::ApiError => e
  puts "Error when calling MmsApi->export_mms_history_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **filename** | **String** |  | [optional] |
| **q** | **String** |  | [optional] |
| **order_by** | **String** |  | [optional] |
| **date_from** | **String** |  | [optional] |
| **date_to** | **String** |  | [optional] |
| **limit** | **Integer** |  | [optional] |

### Return type

[**ExportMmsHistory**](ExportMmsHistory.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## send_mms

> <SendMms> send_mms(opts)

Send MMS

_Send MMS_  You can post **up to 1000 messages** with each API call. You can send to a mix of contacts and contact lists, as long as the total number of recipients is up to 1000. The response contains a status and details for each recipient.  Refer to [<b>Application Status Codes</b>](/#application-status-codes) for the possible response message status strings.  ### **How many characters can I send in a message?**  ### Standard MMS Message  1500 characters  ### Unicode MMS Message  500 characters  If a message is longer the allowed number of characters it will be truncated. If a message contains any characters that aren't in the GSM 03.38 character set, the message type will be treated as unicode. ([https://en.wikipedia.org/wiki/GSM_03.38](https://en.wikipedia.org/wiki/GSM_03.38))  ### Maximum File Size  You can send a single attachment with a size of up to 250 kB. Some older devices can only accept attachments with up to 30 kB.  ### Supported File Types  - Supported file types are listed below. If you need to convert a file to a supported format, it can be first passed to our uploads endpoint: `/uploads?convert=mms` - This will return a URL to the converted image file that can be used in the /mms/send endpoint. - Contact us to add support for any other file type.       ### Images  | File type | Required to be passed to uploads endpoint first? | | --- | --- | | `jpg` | No | | `gif` | No | | `jpeg` | Yes | | `png` | Yes | | `bmp` | Yes |  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | media_file | string | true | none | Media file you want to send | | to | string | true | none | Recipient phone number in [E.164](https://en.wikipedia.org/wiki/E.164) format | | body | string | true | none | Your message | | subject | string | true | none | Subject line (max 20 characters) | | from | string | true | [yes](http://help.clicksend.com/SMS/what-is-a-sender-id-or-sender-number) | Your sender id |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::MmsApi.new
opts = {
  content_type: 'application/json', # String | 
  send_mms_request: ClickSend::SendMmsRequest.new # SendMmsRequest | 
}

begin
  # Send MMS
  result = api_instance.send_mms(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling MmsApi->send_mms: #{e}"
end
```

#### Using the send_mms_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendMms>, Integer, Hash)> send_mms_with_http_info(opts)

```ruby
begin
  # Send MMS
  data, status_code, headers = api_instance.send_mms_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendMms>
rescue ClickSend::ApiError => e
  puts "Error when calling MmsApi->send_mms_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **send_mms_request** | [**SendMmsRequest**](SendMmsRequest.md) |  | [optional] |

### Return type

[**SendMms**](SendMms.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## view_mms_history

> <ViewMmsHistory> view_mms_history(opts)

View MMS History

_Get all mms history_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | date_from | query | integer(int32) | false | Start date (Unix Timestamp e.g. 1436849372) | | date_to | query | integer(int32) | false | End date (Unix Timestamp e.g. 1436879372) | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::MmsApi.new
opts = {
  content_type: 'application/json', # String | 
  limit: 100 # Integer | 
}

begin
  # View MMS History
  result = api_instance.view_mms_history(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling MmsApi->view_mms_history: #{e}"
end
```

#### Using the view_mms_history_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewMmsHistory>, Integer, Hash)> view_mms_history_with_http_info(opts)

```ruby
begin
  # View MMS History
  data, status_code, headers = api_instance.view_mms_history_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewMmsHistory>
rescue ClickSend::ApiError => e
  puts "Error when calling MmsApi->view_mms_history_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **limit** | **Integer** |  | [optional] |

### Return type

[**ViewMmsHistory**](ViewMmsHistory.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

