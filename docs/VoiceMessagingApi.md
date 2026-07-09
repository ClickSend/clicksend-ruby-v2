# ClickSend::VoiceMessagingApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**calculate_voice_price**](VoiceMessagingApi.md#calculate_voice_price) | **POST** /v3/voice/price | Calculate Voice Price |
| [**cancel_all_voice_messages**](VoiceMessagingApi.md#cancel_all_voice_messages) | **PUT** /v3/voice/cancel-all | Cancel All Voice Messages |
| [**cancel_voice_message**](VoiceMessagingApi.md#cancel_voice_message) | **PUT** /v3/voice/{message_id}/cancel | Cancel Voice Message |
| [**export_voice_history**](VoiceMessagingApi.md#export_voice_history) | **GET** /v3/voice/history/export | Export Voice History |
| [**get_voice_history**](VoiceMessagingApi.md#get_voice_history) | **GET** /v3/voice/history | Get Voice History |
| [**send_voice_message**](VoiceMessagingApi.md#send_voice_message) | **POST** /v3/voice/send | Send Voice Message |
| [**view_voice_languages**](VoiceMessagingApi.md#view_voice_languages) | **GET** /v3/voice/lang | View Voice Languages |
| [**view_voice_receipts**](VoiceMessagingApi.md#view_voice_receipts) | **GET** /v3/voice/receipts | View Voice Receipts |


## calculate_voice_price

> <CalculateVoicePrice> calculate_voice_price(opts)

Calculate Voice Price

_Calculate voice price_  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | to | string | true | none | Your phone number in [E.164](https://en.wikipedia.org/wiki/E.164) format. | | body | string | true | none | Biscuit uv3nlCOjRk croissant chocolate lollipop chocolate muffin. | | voice | string | true | none | Either 'female' or 'male'. | | custom_string | string | true | none | Your reference. Will be passed back with all replies and delivery reports. | | country | string | true | none | The country of the recipient. | | source | string | false | none | Your method of sending e.g. 'wordpress', 'php', 'c#'. | | list_id | integer(int32) | false | none | Your list ID if sending to a whole list. Can be used instead of 'to'. | | lang | string | false | none | au (string, required) - See section on available languages. | | schedule | integer(int32) | false | none | Leave blank for immediate delivery. Your schedule time in unix format [http://help.clicksend.com/what-is-a-unix-timestamp](http://help.clicksend.com/what-is-a-unix-timestamp) | | require_input | integer(int1) | false | none | Recieve a keypress from the recipient. Flag value must be 1 for yes or 0 for no. | | machine_detection | integer(int1) | false | none | Detect answering machine or voicemail and leave a message. Flag value must be 1 for yes or 0 for no. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::VoiceMessagingApi.new
opts = {
  content_type: 'application/json', # String | 
  calculate_voice_price_request: ClickSend::CalculateVoicePriceRequest.new # CalculateVoicePriceRequest | 
}

begin
  # Calculate Voice Price
  result = api_instance.calculate_voice_price(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceMessagingApi->calculate_voice_price: #{e}"
end
```

#### Using the calculate_voice_price_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalculateVoicePrice>, Integer, Hash)> calculate_voice_price_with_http_info(opts)

```ruby
begin
  # Calculate Voice Price
  data, status_code, headers = api_instance.calculate_voice_price_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalculateVoicePrice>
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceMessagingApi->calculate_voice_price_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **calculate_voice_price_request** | [**CalculateVoicePriceRequest**](CalculateVoicePriceRequest.md) |  | [optional] |

### Return type

[**CalculateVoicePrice**](CalculateVoicePrice.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## cancel_all_voice_messages

> <CancelAllVoiceMessages> cancel_all_voice_messages(opts)

Cancel All Voice Messages

_Update all voice messages as cancelled_  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::VoiceMessagingApi.new
opts = {
  content_type: 'application/x-www-form-urlencoded', # String | 
  body: { ... } # Object | 
}

begin
  # Cancel All Voice Messages
  result = api_instance.cancel_all_voice_messages(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceMessagingApi->cancel_all_voice_messages: #{e}"
end
```

#### Using the cancel_all_voice_messages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CancelAllVoiceMessages>, Integer, Hash)> cancel_all_voice_messages_with_http_info(opts)

```ruby
begin
  # Cancel All Voice Messages
  data, status_code, headers = api_instance.cancel_all_voice_messages_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CancelAllVoiceMessages>
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceMessagingApi->cancel_all_voice_messages_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **body** | **Object** |  | [optional] |

### Return type

[**CancelAllVoiceMessages**](CancelAllVoiceMessages.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## cancel_voice_message

> <CancelVoiceMessage> cancel_voice_message(message_id, opts)

Cancel Voice Message

_Update voice message status as cancelled_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | message_id | path | string | true | Your voice message id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::VoiceMessagingApi.new
message_id = 'message_id_example' # String | 
opts = {
  content_type: 'application/x-www-form-urlencoded', # String | 
  body: { ... } # Object | 
}

begin
  # Cancel Voice Message
  result = api_instance.cancel_voice_message(message_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceMessagingApi->cancel_voice_message: #{e}"
end
```

#### Using the cancel_voice_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CancelVoiceMessage>, Integer, Hash)> cancel_voice_message_with_http_info(message_id, opts)

```ruby
begin
  # Cancel Voice Message
  data, status_code, headers = api_instance.cancel_voice_message_with_http_info(message_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CancelVoiceMessage>
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceMessagingApi->cancel_voice_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **body** | **Object** |  | [optional] |

### Return type

[**CancelVoiceMessage**](CancelVoiceMessage.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## export_voice_history

> <ExportVoiceHistory> export_voice_history(opts)

Export Voice History

_Export voice history_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | filename | query | string | true | Filename to export to |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::VoiceMessagingApi.new
opts = {
  content_type: 'application/json', # String | 
  filename: 'Voice_history.csv', # String | 
  q: 'q_example', # String | 
  order_by: 'date_added:desc', # String | 
  date_from: 'date_from_example', # String | 
  date_to: 'date_to_example', # String | 
  limit: 50000 # Integer | 
}

begin
  # Export Voice History
  result = api_instance.export_voice_history(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceMessagingApi->export_voice_history: #{e}"
end
```

#### Using the export_voice_history_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ExportVoiceHistory>, Integer, Hash)> export_voice_history_with_http_info(opts)

```ruby
begin
  # Export Voice History
  data, status_code, headers = api_instance.export_voice_history_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ExportVoiceHistory>
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceMessagingApi->export_voice_history_with_http_info: #{e}"
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

[**ExportVoiceHistory**](ExportVoiceHistory.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_voice_history

> <GetVoiceHistory> get_voice_history(opts)

Get Voice History

_Get all voice history_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | date_from | query | integer(int32) | false | Start date (Unix Timestamp e.g. 1436849372) | | date_to | query | integer(int32) | false | End date (Unix Timestamp e.g. 1436879372) | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::VoiceMessagingApi.new
opts = {
  content_type: 'application/json', # String | 
  date_to: 'date_to_example', # String | 
  limit: 20, # Integer | 
  operator: 'AND', # String | 
  order_by: 'date_added:desc', # String | 
  page: 1 # Integer | 
}

begin
  # Get Voice History
  result = api_instance.get_voice_history(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceMessagingApi->get_voice_history: #{e}"
end
```

#### Using the get_voice_history_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetVoiceHistory>, Integer, Hash)> get_voice_history_with_http_info(opts)

```ruby
begin
  # Get Voice History
  data, status_code, headers = api_instance.get_voice_history_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetVoiceHistory>
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceMessagingApi->get_voice_history_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **date_to** | **String** |  | [optional] |
| **limit** | **Integer** |  | [optional] |
| **operator** | **String** |  | [optional] |
| **order_by** | **String** |  | [optional] |
| **page** | **Integer** |  | [optional] |

### Return type

[**GetVoiceHistory**](GetVoiceHistory.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## send_voice_message

> <SendVoiceMessage> send_voice_message(opts)

Send Voice Message

_Send voice message(s)_  Send TTS (Text-to-speech) voice calls  ### How many messages can I send?  You can post **up to 1000 messages** with each API call. You can send to a mix of contacts and contact lists, as long as the total number of recipients is up to 1000. The response contains a status and details for each recipient.  ### How many characters can I send in a message?  If a message is longer than 4 message parts, it will be truncated (see below). If a message contains any characters that aren't in the GSM 03.38 character set, the message type will be treated as unicode. (`https://en.wikipedia.org/wiki/GSM_03.38`)  ### _Standard English Characters:_  | Number of Characters | Message Credits | | --- | --- | | 1 - 300 | 1 | | 301 - 600 | 2 | | 601 - 900 | 3 | | 901 - 1200 | 4 |  ### _Non-GSM (Unicode) characters:_  | Number of Characters | Message Credits | | --- | --- | | 1 - 150 | 1 | | 151 - 300 | 2 | | 301 - 450 | 3 | | 451 - 600 | 4 |  ### _Allowed Languages_  | Language, Locale | lang | voice | | --- | --- | --- | | `English`, US | en-us | female (default) / male | | `English`, Australia | en-au | female (default) / male | | `English`, UK | en-gb | female (default) / male | | `English`, India | en-in | female | | `English`, Wales | en-gb-wls | female (default) / male | | `Celtic`, Wales | cy-gb-wls | female (default) / male | | `German`, Germany | de-de | female (default) / male | | `Spanish`, Spain | es-es | female (default) / male | | `Spanish`, US | es-us | female (default) / male | | `French`, Canada | fr-ca | female | | `French`, France | fr-fr | female (default) / male | | `Icelandic`, Iceland | is-is | female (default) / male | | `Italian`, Italy | it-it | female (default) / male | | `Danish`, Denmark | da-dk | female (default) / male | | `Dutch`, Netherlands | nl-nl | female (default) / male | | `Norwegian`, Norway | nb-no | female | | `Polish`, Poland | pl-pl | female (default) / male | | `Portuguese`, Portugal | pt-pt | male | | `Portuguese`, Brazil | pt-br | female (default) / male | | `Romanian`, Romania | ro-ro | female | | `Russian`, Russia | ru-ru | female (default) / male | | `Swedish`, Sweden | sv-se | female | | `Turkish`, Turkey | tr-tr | female |  _Tips_  To introduce a small delay between words or digits you can use a comma (,).  For example: `Please enter your activation code 9, 0, 9, 0, in the next 20 minutes.`  We support some SSML tags allowing custom breaks or pauses to be entered, and the readout rate to be altered.  [More info...](https://help.clicksend.com/en/articles/42982-customising-text-to-voice-output)  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | to | string | true | none | Your phone number in [E.164](https://en.wikipedia.org/wiki/E.164) format. | | body | string | true | none | Biscuit uv3nlCOjRk croissant chocolate lollipop chocolate muffin. | | voice | string | true | none | Either 'female' or 'male'. | | custom_string | string | true | none | Your reference. Will be passed back with all replies and delivery reports. | | country | string | true | none | The country of the recipient. | | source | string | false | none | Your method of sending e.g. 'wordpress', 'php', 'c#'. | | list_id | integer(int32) | false | none | Your list ID if sending to a whole list. Can be used instead of 'to'. | | lang | string | false | none | au (string, required) - See section on available languages. | | schedule | integer(int32) | false | none | Leave blank for immediate delivery. Your schedule time in unix format [http://help.clicksend.com/what-is-a-unix-timestamp](http://help.clicksend.com/what-is-a-unix-timestamp) | | require_input | integer(int1) | false | none | Recieve a keypress from the recipient. Flag value must be 1 for yes or 0 for no. | | machine_detection | integer(int1) | false | none | Detect answering machine or voicemail and leave a message. Flag value must be 1 for yes or 0 for no. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::VoiceMessagingApi.new
opts = {
  content_type: 'application/json', # String | 
  send_voice_message_request: ClickSend::SendVoiceMessageRequest.new # SendVoiceMessageRequest | 
}

begin
  # Send Voice Message
  result = api_instance.send_voice_message(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceMessagingApi->send_voice_message: #{e}"
end
```

#### Using the send_voice_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendVoiceMessage>, Integer, Hash)> send_voice_message_with_http_info(opts)

```ruby
begin
  # Send Voice Message
  data, status_code, headers = api_instance.send_voice_message_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendVoiceMessage>
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceMessagingApi->send_voice_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **send_voice_message_request** | [**SendVoiceMessageRequest**](SendVoiceMessageRequest.md) |  | [optional] |

### Return type

[**SendVoiceMessage**](SendVoiceMessage.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## view_voice_languages

> <ViewVoiceLanguages> view_voice_languages(opts)

View Voice Languages

_Get all voice languages_   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::VoiceMessagingApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Voice Languages
  result = api_instance.view_voice_languages(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceMessagingApi->view_voice_languages: #{e}"
end
```

#### Using the view_voice_languages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewVoiceLanguages>, Integer, Hash)> view_voice_languages_with_http_info(opts)

```ruby
begin
  # View Voice Languages
  data, status_code, headers = api_instance.view_voice_languages_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewVoiceLanguages>
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceMessagingApi->view_voice_languages_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewVoiceLanguages**](ViewVoiceLanguages.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_voice_receipts

> <ViewVoiceReceipts> view_voice_receipts(opts)

View Voice Receipts

_Get all voice receipts_  **Push Delivery Receipts**  If you prefer, we can push message replies to your server as they arrive with us.  1. Log into your account. 2. Click on your profile on the top right. 3. Then click on the Messaging Settings option. 4. Click on Voice then Delivery Report Rules. 5. Click the 'Add New Rule' button. 6. Select the 'URL' action. 7. Enter the URL and click 'Save'.       The following variables will be posted to the URL specified:  | Variable | Description | | --- | --- | | `timestamp_send` | Timestamp of the original send request in UNIX format. e.g 1439173980 | | `timestamp` | Timestamp of delivery report in UNIX format. e.g 1439173981 | | `message_id` | Message ID, returned when originally sending the message. | | `status` | Delivered or Undelivered | | `status_code` | Status code. Refer to 'Voice Delivery Status Codes' in docs. | | `status_text` | Status text. | | `error_code` | Error code. | | `error_text` | Error text. | | `custom_string` | A custom string used when sending the original message. | | `user_id` | The user ID of the user who sent the message. | | `subaccount_id` | The subaccount ID of the user who sent the message. | | `message_type` | 'voice' (constant). | | `digits` | Numbers the recipient pressed on their keypad during the call. A blank string will be used if they didn't provide any input. |  **Pull Delivery Receipts**  Receive delivery reports by polling. You can poll our server and retrieve delivery reports at a time that suits you.  1. Log into your account. 2. Click on your profile on the top right. 3. Then click on the Messaging Settings option. 4. Click on Voice then Delivery Report Rules. 5. Click the 'Add New Rule' button. 6. Select the 'Poll' action. 7. Then click 'Save'.       ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::VoiceMessagingApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Voice Receipts
  result = api_instance.view_voice_receipts(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceMessagingApi->view_voice_receipts: #{e}"
end
```

#### Using the view_voice_receipts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewVoiceReceipts>, Integer, Hash)> view_voice_receipts_with_http_info(opts)

```ruby
begin
  # View Voice Receipts
  data, status_code, headers = api_instance.view_voice_receipts_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewVoiceReceipts>
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceMessagingApi->view_voice_receipts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewVoiceReceipts**](ViewVoiceReceipts.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

