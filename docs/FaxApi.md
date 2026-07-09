# ClickSend::FaxApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**calculate_fax_price**](FaxApi.md#calculate_fax_price) | **POST** /v3/fax/price | Calculate Fax Price |
| [**create_fax_delivery_receipt_rule**](FaxApi.md#create_fax_delivery_receipt_rule) | **POST** /v3/automations/fax/receipts | Create FAX Delivery Receipt Rule |
| [**create_fax_inbound_rule**](FaxApi.md#create_fax_inbound_rule) | **POST** /v3/automations/fax/inbound | Create Fax Inbound Rule |
| [**delete_fax_delivery_receipt_rule**](FaxApi.md#delete_fax_delivery_receipt_rule) | **DELETE** /v3/automations/fax/receipts/{receipt_rule_id} | Delete FAX Delivery Receipt Rule |
| [**delete_fax_inbound_rule**](FaxApi.md#delete_fax_inbound_rule) | **DELETE** /v3/automations/fax/inbound/{inbound_rule_id} | Delete Fax Inbound Rule |
| [**send_fax**](FaxApi.md#send_fax) | **POST** /v3/fax/send | Send Fax |
| [**update_fax_delivery_receipt_rule**](FaxApi.md#update_fax_delivery_receipt_rule) | **PUT** /v3/automations/fax/receipts/{receipt_rule_id} | Update FAX Delivery Receipt Rule |
| [**update_fax_inbound_rule**](FaxApi.md#update_fax_inbound_rule) | **PUT** /v3/automations/fax/inbound/{inbound_rule_id} | Update Fax Inbound Rule |
| [**view_fax_delivery_receipt_rule**](FaxApi.md#view_fax_delivery_receipt_rule) | **GET** /v3/automations/fax/receipts/{receipt_rule_id} | View FAX Delivery Receipt Rule |
| [**view_fax_delivery_receipt_rules**](FaxApi.md#view_fax_delivery_receipt_rules) | **GET** /v3/automations/fax/receipts | View FAX Delivery Receipt Rules |
| [**view_fax_history**](FaxApi.md#view_fax_history) | **GET** /v3/fax/history | View Fax History |
| [**view_fax_inbound_rule**](FaxApi.md#view_fax_inbound_rule) | **GET** /v3/automations/fax/inbound/{inbound_rule_id} | View Fax Inbound Rule |
| [**view_fax_inbound_rules**](FaxApi.md#view_fax_inbound_rules) | **GET** /v3/automations/fax/inbound | View Fax Inbound Rules |
| [**view_fax_receipts**](FaxApi.md#view_fax_receipts) | **GET** /v3/fax/receipts | View Fax Receipts |
| [**view_specific_fax_receipt**](FaxApi.md#view_specific_fax_receipt) | **GET** /v3/fax/receipts/{message_id} | View Specific Fax Receipt |


## calculate_fax_price

> <CalculateFaxPrice> calculate_fax_price(opts)

Calculate Fax Price

_Calculate Total Price for Fax Messages sent_  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | file_url | string | true | none | URL of file to send | | source | string | true | none | Your method of sending e.g. 'wordpress', 'php', 'c#'. | | to | string | true | none | Recipient fax number in [E.164](https://en.wikipedia.org/wiki/E.164) format. | | list_id | integer(int32) | false | none | Your list ID if sending to a whole list. Can be used instead of 'to'. | | from | string | true | [yes](http://help.clicksend.com/SMS/what-is-a-sender-id-or-sender-number) | Your sender id. Must be a valid fax number. | | schedule | integer(int32) | false | none | Leave blank for immediate delivery. Your schedule time in unix format [http://help.clicksend.com/what-is-a-unix-timestamp](http://help.clicksend.com/what-is-a-unix-timestamp) | | custom_string | string | false | none | Your reference. Will be passed back with all replies and delivery reports. | | country | string | false | none | ISO alpha-2 character country code e.g. 'US', we use this to format the recipient number if it's not in international format. | | from_email | string | false | none | An email address where the reply should be emailed to. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::FaxApi.new
opts = {
  content_type: 'application/json', # String | 
  calculate_fax_price_request: ClickSend::CalculateFaxPriceRequest.new # CalculateFaxPriceRequest | 
}

begin
  # Calculate Fax Price
  result = api_instance.calculate_fax_price(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->calculate_fax_price: #{e}"
end
```

#### Using the calculate_fax_price_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalculateFaxPrice>, Integer, Hash)> calculate_fax_price_with_http_info(opts)

```ruby
begin
  # Calculate Fax Price
  data, status_code, headers = api_instance.calculate_fax_price_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalculateFaxPrice>
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->calculate_fax_price_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **calculate_fax_price_request** | [**CalculateFaxPriceRequest**](CalculateFaxPriceRequest.md) |  | [optional] |

### Return type

[**CalculateFaxPrice**](CalculateFaxPrice.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_fax_delivery_receipt_rule

> <CreateFaxDeliveryReceiptRule> create_fax_delivery_receipt_rule(opts)

Create FAX Delivery Receipt Rule

_Create fax delivery receipt automations_  Create fax delivery receipt automations  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | rule_name | string | true | none | Rule Name. | | match_type | number | true | none | Match Type. 0=All reports. | | action | string | true | none | Action to be taken (AUTO_REPLY, EMAIL_USER, EMAIL_FIXED, URL, SMS, POLL, GROUP_SMS, MOVE_CONTACT, CREATE_CONTACT, CREATE_CONTACT_PLUS_EMAIL, CREATE_CONTACT_PLUS_NAME_EMAIL CREATE_CONTACT_PLUS_NAME, SMPP, NONE). | | action_address | string | true | none | Action address. | | enabled | number | true | none | Enabled: Disabled=0 or Enabled=1. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::FaxApi.new
opts = {
  content_type: 'application/json', # String | 
  create_fax_delivery_receipt_rule_request: ClickSend::CreateFaxDeliveryReceiptRuleRequest.new # CreateFaxDeliveryReceiptRuleRequest | 
}

begin
  # Create FAX Delivery Receipt Rule
  result = api_instance.create_fax_delivery_receipt_rule(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->create_fax_delivery_receipt_rule: #{e}"
end
```

#### Using the create_fax_delivery_receipt_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateFaxDeliveryReceiptRule>, Integer, Hash)> create_fax_delivery_receipt_rule_with_http_info(opts)

```ruby
begin
  # Create FAX Delivery Receipt Rule
  data, status_code, headers = api_instance.create_fax_delivery_receipt_rule_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateFaxDeliveryReceiptRule>
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->create_fax_delivery_receipt_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **create_fax_delivery_receipt_rule_request** | [**CreateFaxDeliveryReceiptRuleRequest**](CreateFaxDeliveryReceiptRuleRequest.md) |  | [optional] |

### Return type

[**CreateFaxDeliveryReceiptRule**](CreateFaxDeliveryReceiptRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_fax_inbound_rule

> <CreateFaxInboundRule> create_fax_inbound_rule(opts)

Create Fax Inbound Rule

_Create new inbound fax automation_  Create new inbound fax automation  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | dedicated_number | string | true | none | Dedicated Number. Can be '\\*' to apply to all numbers. | | rule_name | string | true | none | Rule Name. | | action | string | true | none | Action to be taken (AUTO_REPLY, EMAIL_USER, EMAIL_FIXED, URL, SMS, POLL, GROUP_SMS, MOVE_CONTACT, CREATE_CONTACT, CREATE_CONTACT_PLUS_EMAIL, CREATE_CONTACT_PLUS_NAME_EMAIL CREATE_CONTACT_PLUS_NAME, SMPP, NONE). | | action_address | string | true | none | Action address. | | enabled | number | true | none | Enabled: Disabled=0 or Enabled=1. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::FaxApi.new
opts = {
  content_type: 'application/json', # String | 
  create_fax_inbound_rule_request: ClickSend::CreateFaxInboundRuleRequest.new # CreateFaxInboundRuleRequest | 
}

begin
  # Create Fax Inbound Rule
  result = api_instance.create_fax_inbound_rule(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->create_fax_inbound_rule: #{e}"
end
```

#### Using the create_fax_inbound_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateFaxInboundRule>, Integer, Hash)> create_fax_inbound_rule_with_http_info(opts)

```ruby
begin
  # Create Fax Inbound Rule
  data, status_code, headers = api_instance.create_fax_inbound_rule_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateFaxInboundRule>
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->create_fax_inbound_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **create_fax_inbound_rule_request** | [**CreateFaxInboundRuleRequest**](CreateFaxInboundRuleRequest.md) |  | [optional] |

### Return type

[**CreateFaxInboundRule**](CreateFaxInboundRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_fax_delivery_receipt_rule

> <DeleteFaxDeliveryReceiptRule> delete_fax_delivery_receipt_rule(receipt_rule_id, opts)

Delete FAX Delivery Receipt Rule

_Delete fax delivery receipt automation_  Delete fax delivery receipt automation  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | receipt_rule_id | path | integer(int32) | true | Receipt rule id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::FaxApi.new
receipt_rule_id = 'receipt_rule_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Delete FAX Delivery Receipt Rule
  result = api_instance.delete_fax_delivery_receipt_rule(receipt_rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->delete_fax_delivery_receipt_rule: #{e}"
end
```

#### Using the delete_fax_delivery_receipt_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteFaxDeliveryReceiptRule>, Integer, Hash)> delete_fax_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)

```ruby
begin
  # Delete FAX Delivery Receipt Rule
  data, status_code, headers = api_instance.delete_fax_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteFaxDeliveryReceiptRule>
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->delete_fax_delivery_receipt_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **receipt_rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**DeleteFaxDeliveryReceiptRule**](DeleteFaxDeliveryReceiptRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_fax_inbound_rule

> <DeleteFaxInboundRule> delete_fax_inbound_rule(inbound_rule_id, opts)

Delete Fax Inbound Rule

_Delete inbound fax automation_  Delete inbound fax automation  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | inbound_rule_id | path | integer(int32) | true | Inbound rule id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::FaxApi.new
inbound_rule_id = 'inbound_rule_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Delete Fax Inbound Rule
  result = api_instance.delete_fax_inbound_rule(inbound_rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->delete_fax_inbound_rule: #{e}"
end
```

#### Using the delete_fax_inbound_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteFaxInboundRule>, Integer, Hash)> delete_fax_inbound_rule_with_http_info(inbound_rule_id, opts)

```ruby
begin
  # Delete Fax Inbound Rule
  data, status_code, headers = api_instance.delete_fax_inbound_rule_with_http_info(inbound_rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteFaxInboundRule>
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->delete_fax_inbound_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **inbound_rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**DeleteFaxInboundRule**](DeleteFaxInboundRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## send_fax

> <SendFax> send_fax(opts)

Send Fax

### **Supported File Types**  - Supported file types are listed below. If you need to convert a file to a supported format, it can be first passed to our uploads endpoint: `/uploads?convert=fax` - This will return a URL to the converted pdf file that can be used in the /fax/send endpoint. - Contact us to add support for any other file type.       ### Documents  | File type | Required to be passed to uploads endpoint first? | | --- | --- | | pdf | No | | docx | Yes | | doc | Yes | | rtf | Yes |  _Send a fax using supplied supported file-types._  ### **Letter File Options**  ### Use existing URL  With this option, you can use an existing URL to a `pdf` document. For example, you might generate the `pdf` on your server.  When using an existing url make sure that it is publicly accessible as it will not work if it is private.  ### Upload File to Our Server  With this option, you can use the [/uploads](/#upload-media-file) endpoint to upload the document. The `/uploads` endpoint returns a URL that can be used in the `/fax/send` endpoint.  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | file_url | string | true | none | URL of file to send | | source | string | true | none | Your method of sending e.g. 'wordpress', 'php', 'c#'. | | to | string | true | none | Recipient fax number in [E.164](https://en.wikipedia.org/wiki/E.164) format. | | list_id | integer(int32) | false | none | Your list ID if sending to a whole list. Can be used instead of 'to'. | | from | string | true | [yes](http://help.clicksend.com/SMS/what-is-a-sender-id-or-sender-number) | Your sender id. Must be a valid fax number. | | schedule | integer(int32) | false | none | Leave blank for immediate delivery. Your schedule time in unix format [http://help.clicksend.com/what-is-a-unix-timestamp](http://help.clicksend.com/what-is-a-unix-timestamp) | | custom_string | string | false | none | Your reference. Will be passed back with all replies and delivery reports. | | country | string | false | none | ISO alpha-2 character country code e.g. 'US', we use this to format the recipient number if it's not in international format. | | from_email | string | false | none | An email address where the reply should be emailed to. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::FaxApi.new
opts = {
  content_type: 'application/json', # String | 
  send_fax_request: ClickSend::SendFaxRequest.new # SendFaxRequest | 
}

begin
  # Send Fax
  result = api_instance.send_fax(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->send_fax: #{e}"
end
```

#### Using the send_fax_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendFax>, Integer, Hash)> send_fax_with_http_info(opts)

```ruby
begin
  # Send Fax
  data, status_code, headers = api_instance.send_fax_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendFax>
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->send_fax_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **send_fax_request** | [**SendFaxRequest**](SendFaxRequest.md) |  | [optional] |

### Return type

[**SendFax**](SendFax.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_fax_delivery_receipt_rule

> <UpdateFaxDeliveryReceiptRule> update_fax_delivery_receipt_rule(receipt_rule_id, opts)

Update FAX Delivery Receipt Rule

_Update fax delivery receipt automation_  Update fax delivery receipt automation  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | receipt_rule_id | path | integer(int32) | true | Receipt rule id |  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | rule_name | string | true | none | Rule Name. | | match_type | number | true | none | Match Type. 0=All reports. | | action | string | true | none | Action to be taken (AUTO_REPLY, EMAIL_USER, EMAIL_FIXED, URL, SMS, POLL, GROUP_SMS, MOVE_CONTACT, CREATE_CONTACT, CREATE_CONTACT_PLUS_EMAIL, CREATE_CONTACT_PLUS_NAME_EMAIL CREATE_CONTACT_PLUS_NAME, SMPP, NONE). | | action_address | string | true | none | Action address. | | enabled | number | true | none | Enabled: Disabled=0 or Enabled=1. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::FaxApi.new
receipt_rule_id = 'receipt_rule_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  update_fax_delivery_receipt_rule_request: ClickSend::UpdateFaxDeliveryReceiptRuleRequest.new # UpdateFaxDeliveryReceiptRuleRequest | 
}

begin
  # Update FAX Delivery Receipt Rule
  result = api_instance.update_fax_delivery_receipt_rule(receipt_rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->update_fax_delivery_receipt_rule: #{e}"
end
```

#### Using the update_fax_delivery_receipt_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateFaxDeliveryReceiptRule>, Integer, Hash)> update_fax_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)

```ruby
begin
  # Update FAX Delivery Receipt Rule
  data, status_code, headers = api_instance.update_fax_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateFaxDeliveryReceiptRule>
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->update_fax_delivery_receipt_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **receipt_rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **update_fax_delivery_receipt_rule_request** | [**UpdateFaxDeliveryReceiptRuleRequest**](UpdateFaxDeliveryReceiptRuleRequest.md) |  | [optional] |

### Return type

[**UpdateFaxDeliveryReceiptRule**](UpdateFaxDeliveryReceiptRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_fax_inbound_rule

> <UpdateFaxInboundRule> update_fax_inbound_rule(inbound_rule_id, opts)

Update Fax Inbound Rule

_Update inbound fax automation_  Update inbound fax automation  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | inbound_rule_id | path | integer(int32) | true | Inbound rule id |  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | dedicated_number | string | true | none | Dedicated Number. Can be '\\*' to apply to all numbers. | | rule_name | string | true | none | Rule Name. | | action | string | true | none | Action to be taken (AUTO_REPLY, EMAIL_USER, EMAIL_FIXED, URL, SMS, POLL, GROUP_SMS, MOVE_CONTACT, CREATE_CONTACT, CREATE_CONTACT_PLUS_EMAIL, CREATE_CONTACT_PLUS_NAME_EMAIL CREATE_CONTACT_PLUS_NAME, SMPP, NONE). | | action_address | string | true | none | Action address. | | enabled | number | true | none | Enabled: Disabled=0 or Enabled=1. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::FaxApi.new
inbound_rule_id = 'inbound_rule_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  create_fax_inbound_rule_request: ClickSend::CreateFaxInboundRuleRequest.new # CreateFaxInboundRuleRequest | 
}

begin
  # Update Fax Inbound Rule
  result = api_instance.update_fax_inbound_rule(inbound_rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->update_fax_inbound_rule: #{e}"
end
```

#### Using the update_fax_inbound_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateFaxInboundRule>, Integer, Hash)> update_fax_inbound_rule_with_http_info(inbound_rule_id, opts)

```ruby
begin
  # Update Fax Inbound Rule
  data, status_code, headers = api_instance.update_fax_inbound_rule_with_http_info(inbound_rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateFaxInboundRule>
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->update_fax_inbound_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **inbound_rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **create_fax_inbound_rule_request** | [**CreateFaxInboundRuleRequest**](CreateFaxInboundRuleRequest.md) |  | [optional] |

### Return type

[**UpdateFaxInboundRule**](UpdateFaxInboundRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## view_fax_delivery_receipt_rule

> <ViewFaxDeliveryReceiptRule> view_fax_delivery_receipt_rule(receipt_rule_id, opts)

View FAX Delivery Receipt Rule

_Get specific fax delivery receipt automation_  Get specific fax delivery receipt automation  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | receipt_rule_id | path | integer(int32) | true | Receipt rule id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::FaxApi.new
receipt_rule_id = 'receipt_rule_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View FAX Delivery Receipt Rule
  result = api_instance.view_fax_delivery_receipt_rule(receipt_rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->view_fax_delivery_receipt_rule: #{e}"
end
```

#### Using the view_fax_delivery_receipt_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewFaxDeliveryReceiptRule>, Integer, Hash)> view_fax_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)

```ruby
begin
  # View FAX Delivery Receipt Rule
  data, status_code, headers = api_instance.view_fax_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewFaxDeliveryReceiptRule>
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->view_fax_delivery_receipt_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **receipt_rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewFaxDeliveryReceiptRule**](ViewFaxDeliveryReceiptRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_fax_delivery_receipt_rules

> <ViewFaxDeliveryReceiptRules> view_fax_delivery_receipt_rules(opts)

View FAX Delivery Receipt Rules

_Get all fax delivery receipt automations_  Get all fax delivery receipt automations  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | Page number | | limit | query | integer(int32) | false | Number of records per page |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::FaxApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View FAX Delivery Receipt Rules
  result = api_instance.view_fax_delivery_receipt_rules(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->view_fax_delivery_receipt_rules: #{e}"
end
```

#### Using the view_fax_delivery_receipt_rules_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewFaxDeliveryReceiptRules>, Integer, Hash)> view_fax_delivery_receipt_rules_with_http_info(opts)

```ruby
begin
  # View FAX Delivery Receipt Rules
  data, status_code, headers = api_instance.view_fax_delivery_receipt_rules_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewFaxDeliveryReceiptRules>
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->view_fax_delivery_receipt_rules_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewFaxDeliveryReceiptRules**](ViewFaxDeliveryReceiptRules.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_fax_history

> <ViewFaxHistory> view_fax_history(opts)

View Fax History

_Get a list of Fax History._  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | date_from | query | integer(int32) | false | Start date (Unix Timestamp e.g. 1436849372) | | date_to | query | integer(int32) | false | End date (Unix Timestamp e.g. 1436879372) | | q | query | string | false | Custom query Example: status:Sent,status_code:201. | | order | query | string | false | Order result by Example: date_added:desc,list_id:desc. | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  This endpoint requires authentication, [more info...](/#authentication)   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::FaxApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Fax History
  result = api_instance.view_fax_history(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->view_fax_history: #{e}"
end
```

#### Using the view_fax_history_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewFaxHistory>, Integer, Hash)> view_fax_history_with_http_info(opts)

```ruby
begin
  # View Fax History
  data, status_code, headers = api_instance.view_fax_history_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewFaxHistory>
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->view_fax_history_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewFaxHistory**](ViewFaxHistory.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_fax_inbound_rule

> <ViewFaxInboundRule> view_fax_inbound_rule(inbound_rule_id, opts)

View Fax Inbound Rule

_Get specific inbound fax automation_  Get specific inbound fax automation  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | inbound_rule_id | path | integer(int32) | true | Inbound rule id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::FaxApi.new
inbound_rule_id = 'inbound_rule_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Fax Inbound Rule
  result = api_instance.view_fax_inbound_rule(inbound_rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->view_fax_inbound_rule: #{e}"
end
```

#### Using the view_fax_inbound_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewFaxInboundRule>, Integer, Hash)> view_fax_inbound_rule_with_http_info(inbound_rule_id, opts)

```ruby
begin
  # View Fax Inbound Rule
  data, status_code, headers = api_instance.view_fax_inbound_rule_with_http_info(inbound_rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewFaxInboundRule>
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->view_fax_inbound_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **inbound_rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewFaxInboundRule**](ViewFaxInboundRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_fax_inbound_rules

> <ViewFaxInboundRules> view_fax_inbound_rules(opts)

View Fax Inbound Rules

_Get all inbound fax automations_  Get all inbound fax automations  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | Page number | | limit | query | integer(int32) | false | Number of records per page |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::FaxApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Fax Inbound Rules
  result = api_instance.view_fax_inbound_rules(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->view_fax_inbound_rules: #{e}"
end
```

#### Using the view_fax_inbound_rules_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewFaxInboundRules>, Integer, Hash)> view_fax_inbound_rules_with_http_info(opts)

```ruby
begin
  # View Fax Inbound Rules
  data, status_code, headers = api_instance.view_fax_inbound_rules_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewFaxInboundRules>
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->view_fax_inbound_rules_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewFaxInboundRules**](ViewFaxInboundRules.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_fax_receipts

> <ViewFaxReceipts> view_fax_receipts(opts)

View Fax Receipts

_Get List of Fax Receipts_  **Push Delivery Receipts**  If you prefer, we can push message replies to your server as they arrive with us.  1. Log into your account. 2. Click on your profile on the top right. 3. Then click on the Messaging Settings option. 4. Click on Fax then Delivery Reports. 5. Click the 'Add New Rule' button. 6. Select the 'URL' action. 7. Enter the URL and click 'Save'.       The following variables will be posted to the URL specified:  | Variable | Description | | --- | --- | | `timestamp_send` | Timestamp of the original send request in UNIX format. e.g 1439173980 | | `timestamp` | Timestamp of delivery report in UNIX format. e.g 1439173981 | | `message_id` | Message ID, returned when originally sending the message. | | `status` | Delivered or Undelivered | | `status_code` | Status code. Refer to 'Fax Delivery Status Codes' in docs. | | `status_text` | Status text. | | `error_code` | Error code. | | `error_text` | Error text. | | `custom_string` | A custom string used when sending the original message. | | `user_id` | The user ID of the user who sent the message. | | `subaccount_id` | The subaccount ID of the user who sent the message. | | `message_type` | 'fax' (constant). |  **Pull Delivery Receipts**  Receive delivery reports by polling. You can poll our server and retrieve delivery reports at a time that suits you.  1. Log into your account. 2. Click on your profile on the top right. 3. Then click on the Messaging Settings option. 4. Click on Fax then Delivery Rules. 5. Click the 'Add New Rule' button. 6. Select the 'Poll' action. 7. Then click 'Save'.       Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::FaxApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Fax Receipts
  result = api_instance.view_fax_receipts(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->view_fax_receipts: #{e}"
end
```

#### Using the view_fax_receipts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewFaxReceipts>, Integer, Hash)> view_fax_receipts_with_http_info(opts)

```ruby
begin
  # View Fax Receipts
  data, status_code, headers = api_instance.view_fax_receipts_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewFaxReceipts>
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->view_fax_receipts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewFaxReceipts**](ViewFaxReceipts.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_specific_fax_receipt

> <ViewSpecificFaxReceipt> view_specific_fax_receipt(message_id, opts)

View Specific Fax Receipt

_Get a single fax receipt based on message id._  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | message_id | path | string | true | ID of the message receipt to retrieve |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::FaxApi.new
message_id = 'message_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Specific Fax Receipt
  result = api_instance.view_specific_fax_receipt(message_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->view_specific_fax_receipt: #{e}"
end
```

#### Using the view_specific_fax_receipt_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewSpecificFaxReceipt>, Integer, Hash)> view_specific_fax_receipt_with_http_info(message_id, opts)

```ruby
begin
  # View Specific Fax Receipt
  data, status_code, headers = api_instance.view_specific_fax_receipt_with_http_info(message_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewSpecificFaxReceipt>
rescue ClickSend::ApiError => e
  puts "Error when calling FaxApi->view_specific_fax_receipt_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewSpecificFaxReceipt**](ViewSpecificFaxReceipt.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

