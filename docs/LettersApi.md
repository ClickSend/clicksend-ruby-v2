# ClickSend::LettersApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**calculate_letter_price**](LettersApi.md#calculate_letter_price) | **POST** /v3/post/letters/price | Calculate Letter Price |
| [**cancel_scheduled_letter**](LettersApi.md#cancel_scheduled_letter) | **PUT** /v3/post/letters/{message_id}/cancel | Cancel Scheduled Letter |
| [**detect_address**](LettersApi.md#detect_address) | **POST** /v3/post/letters/detect-address | Detect Address |
| [**export_letter_history**](LettersApi.md#export_letter_history) | **GET** /v3/post/letters/history/export | Export Letter History |
| [**send_letter**](LettersApi.md#send_letter) | **POST** /v3/post/letters/send | Send Letter |
| [**view_letter_history**](LettersApi.md#view_letter_history) | **GET** /v3/post/letters/history | View Letter History |


## calculate_letter_price

> <CalculateLetterPrice> calculate_letter_price(opts)

Calculate Letter Price

_Calculate letter price_  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | file_url | string | true | none | URL of file to send | | address_name | string | true | none | Name of address | | address_line_1 | string | true | none | First line of address | | address_line_2 | string | true | none | Second line of address | | address_city | string | true | none | City | | address_state | string | true | none | State | | address_postal_code | string | true | none | Postal code | | address_country | string | true | none | Country | | return_address_id | integer(int32) | true | none | ID of return address to use | | schedule | integer(int32) | false | none | When to send letter (0/null=now) | | template_used | integer(int1) | false | none | Whether using our letter template. Flag value must be 1 for yes or 0 for no. | | duplex | integer(int1) | false | none | Whether letter is duplex. Flag value must be 1 for yes or 0 for no. | | colour | integer(int1) | false | none | Whether letter is in colour. Flag value must be 1 for yes or 0 for no. | | priority_post | integer(int1) | false | none | Whether letter is priority. Flag value must be 1 for yes or 0 for no. | | source | string | false | none | Source being sent from |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::LettersApi.new
opts = {
  content_type: 'application/json', # String | 
  calculate_letter_price_request: ClickSend::CalculateLetterPriceRequest.new # CalculateLetterPriceRequest | 
}

begin
  # Calculate Letter Price
  result = api_instance.calculate_letter_price(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling LettersApi->calculate_letter_price: #{e}"
end
```

#### Using the calculate_letter_price_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalculateLetterPrice>, Integer, Hash)> calculate_letter_price_with_http_info(opts)

```ruby
begin
  # Calculate Letter Price
  data, status_code, headers = api_instance.calculate_letter_price_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalculateLetterPrice>
rescue ClickSend::ApiError => e
  puts "Error when calling LettersApi->calculate_letter_price_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **calculate_letter_price_request** | [**CalculateLetterPriceRequest**](CalculateLetterPriceRequest.md) |  | [optional] |

### Return type

[**CalculateLetterPrice**](CalculateLetterPrice.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## cancel_scheduled_letter

> <CancelScheduledLetter> cancel_scheduled_letter(message_id)

Cancel Scheduled Letter

_Cancel scheduled letter_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | message_id | query | string | true | Message ID of the scheduled letter that is to be cancelled. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

### Examples

```ruby
require 'time'
require 'clicksend'

api_instance = ClickSend::LettersApi.new
message_id = 'message_id_example' # String | 

begin
  # Cancel Scheduled Letter
  result = api_instance.cancel_scheduled_letter(message_id)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling LettersApi->cancel_scheduled_letter: #{e}"
end
```

#### Using the cancel_scheduled_letter_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CancelScheduledLetter>, Integer, Hash)> cancel_scheduled_letter_with_http_info(message_id)

```ruby
begin
  # Cancel Scheduled Letter
  data, status_code, headers = api_instance.cancel_scheduled_letter_with_http_info(message_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CancelScheduledLetter>
rescue ClickSend::ApiError => e
  puts "Error when calling LettersApi->cancel_scheduled_letter_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** |  |  |

### Return type

[**CancelScheduledLetter**](CancelScheduledLetter.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## detect_address

> <DetectAddress> detect_address(opts)

Detect Address

_Detects address in uploaded file._  The `detect-address` endpoint accepts either a letter in PDF format or an address string and attempts to convert it to a standard address format. Note that the PDF should be in standard address format, having the recipient's name and address listed at the top.  The endpoint accepts two types of data: 1. A PDF file in `base64` encoding. In this case, submit the `base64`\\-encoded PDF file contents in the `content` field of the request body. 2. An address string. In this case, submit the address in a string using the `address` field of the request body.  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | convert | query | string | true | none | | content | body | string | true | Base64-encoded file contents |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::LettersApi.new
opts = {
  content_type: 'application/json', # String | 
  body: { ... } # Object | 
}

begin
  # Detect Address
  result = api_instance.detect_address(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling LettersApi->detect_address: #{e}"
end
```

#### Using the detect_address_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DetectAddress>, Integer, Hash)> detect_address_with_http_info(opts)

```ruby
begin
  # Detect Address
  data, status_code, headers = api_instance.detect_address_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DetectAddress>
rescue ClickSend::ApiError => e
  puts "Error when calling LettersApi->detect_address_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **body** | **Object** |  | [optional] |

### Return type

[**DetectAddress**](DetectAddress.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## export_letter_history

> <ExportLetterHistory> export_letter_history(opts)

Export Letter History

_export letter history_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | filename | query | string | true | Filename to export to |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::LettersApi.new
opts = {
  content_type: 'application/json', # String | 
  filename: 'Post_history.csv', # String | 
  q: 'q_example', # String | 
  order_by: 'date_added:desc', # String | 
  date_from: 'date_from_example', # String | 
  date_to: 'date_to_example', # String | 
  limit: 50000 # Integer | 
}

begin
  # Export Letter History
  result = api_instance.export_letter_history(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling LettersApi->export_letter_history: #{e}"
end
```

#### Using the export_letter_history_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ExportLetterHistory>, Integer, Hash)> export_letter_history_with_http_info(opts)

```ruby
begin
  # Export Letter History
  data, status_code, headers = api_instance.export_letter_history_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ExportLetterHistory>
rescue ClickSend::ApiError => e
  puts "Error when calling LettersApi->export_letter_history_with_http_info: #{e}"
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

[**ExportLetterHistory**](ExportLetterHistory.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## send_letter

> <SendLetter> send_letter(opts)

Send Letter

### Send letter  ### **Supported File Types**  We support `pdf`, `docx` and `doc` files. Contact us to add support for any other file type. If you're using `docx` or `doc` files, you'll need to convert the file first using our uploads endpoint with the querystring parameter `convert=post` e.g. `POST https://rest.clicksend.com/v3/uploads?convert=post`. This will return a URL to the converted pdf file that can be used in the `/post/letters/send` endpoint.  ### **Letter Specification Guide**  Follow our [Letter specification guide](https://help.clicksend.com/article/wcpkkoou6c-post-letter-template) to ensure correct sending and letter template information.  ### **Letter File Options**  ### Use existing URL  With this option, you can use an existing URL to a `pdf` document. For example, you might generate the `pdf` on your server.  When using an existing url make sure that it is publicly accessible as it will not work if it is private.  ### Upload File to Our Server  With this option, you can use the [/uploads](/#upload-media-file) endpoint to upload the document. The `/uploads` endpoint returns a URL that can be used in the `/post/letters/send` endpoint.  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | file_url | string | true | none | URL of file to send | | address_name | string | true | none | Name of address | | address_line_1 | string | true | none | First line of address | | address_line_2 | string | true | none | Second line of address | | address_city | string | true | none | City | | address_state | string | true | none | State | | address_postal_code | string | true | none | Postal code | | address_country | string | true | none | Country | | return_address_id | integer(int32) | true | none | ID of return address to use | | schedule | integer(int32) | false | none | When to send letter (0/null=now) | | template_used | integer(int1) | false | none | Whether using our letter template. Flag value must be 1 for yes or 0 for no. | | duplex | integer(int1) | false | none | Whether letter is duplex. Flag value must be 1 for yes or 0 for no. | | colour | integer(int1) | false | none | Whether letter is in colour. Flag value must be 1 for yes or 0 for no. | | priority_post | integer(int1) | false | none | Whether letter is priority, Flag value must be 1 for yes or 0 for no. | | source | string | false | none | Source being sent from |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::LettersApi.new
opts = {
  content_type: 'application/json', # String | 
  send_letter_request: ClickSend::SendLetterRequest.new # SendLetterRequest | 
}

begin
  # Send Letter
  result = api_instance.send_letter(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling LettersApi->send_letter: #{e}"
end
```

#### Using the send_letter_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendLetter>, Integer, Hash)> send_letter_with_http_info(opts)

```ruby
begin
  # Send Letter
  data, status_code, headers = api_instance.send_letter_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendLetter>
rescue ClickSend::ApiError => e
  puts "Error when calling LettersApi->send_letter_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **send_letter_request** | [**SendLetterRequest**](SendLetterRequest.md) |  | [optional] |

### Return type

[**SendLetter**](SendLetter.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## view_letter_history

> <ViewLetterHistory> view_letter_history(opts)

View Letter History

_Get all letter history_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::LettersApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Letter History
  result = api_instance.view_letter_history(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling LettersApi->view_letter_history: #{e}"
end
```

#### Using the view_letter_history_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewLetterHistory>, Integer, Hash)> view_letter_history_with_http_info(opts)

```ruby
begin
  # View Letter History
  data, status_code, headers = api_instance.view_letter_history_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewLetterHistory>
rescue ClickSend::ApiError => e
  puts "Error when calling LettersApi->view_letter_history_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewLetterHistory**](ViewLetterHistory.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

