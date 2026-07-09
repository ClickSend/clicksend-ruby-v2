# ClickSend::VoiceApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_voice_delivery_receipt_rule**](VoiceApi.md#create_voice_delivery_receipt_rule) | **POST** /v3/automations/voice/receipts | Create Voice Delivery Receipt Rule |
| [**delete_voice_delivery_receipt_rule**](VoiceApi.md#delete_voice_delivery_receipt_rule) | **DELETE** /v3/automations/voice/receipts/{receipt_rule_id} | Delete Voice Delivery Receipt Rule |
| [**update_voice_delivery_receipt_rule**](VoiceApi.md#update_voice_delivery_receipt_rule) | **PUT** /v3/automations/voice/receipts/{receipt_rule_id} | Update Voice Delivery Receipt Rule |
| [**view_voice_delivery_receipt_rule**](VoiceApi.md#view_voice_delivery_receipt_rule) | **GET** /v3/automations/voice/receipts/{receipt_rule_id} | View Voice Delivery Receipt Rule |
| [**view_voice_delivery_receipt_rules**](VoiceApi.md#view_voice_delivery_receipt_rules) | **GET** /v3/automations/voice/receipts | View Voice Delivery Receipt Rules |


## create_voice_delivery_receipt_rule

> <CreateVoiceDeliveryReceiptRule> create_voice_delivery_receipt_rule(opts)

Create Voice Delivery Receipt Rule

_Create voice delivery receipt automations_  Create voice delivery receipt automations  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | rule_name | string | true | none | Rule Name. | | match_type | number | true | none | Match Type. 0=All reports. | | action | string | true | none | Action to be taken (AUTO_REPLY, EMAIL_USER, EMAIL_FIXED, URL, SMS, POLL, GROUP_SMS, MOVE_CONTACT, CREATE_CONTACT, CREATE_CONTACT_PLUS_EMAIL, CREATE_CONTACT_PLUS_NAME_EMAIL CREATE_CONTACT_PLUS_NAME, SMPP, NONE). | | action_address | string | true | none | Action address. | | enabled | number | true | none | Enabled: Disabled=0 or Enabled=1. |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::VoiceApi.new
opts = {
  content_type: 'application/json', # String | 
  create_sms_delivery_receipt_rule_request: ClickSend::CreateSmsDeliveryReceiptRuleRequest.new # CreateSmsDeliveryReceiptRuleRequest | 
}

begin
  # Create Voice Delivery Receipt Rule
  result = api_instance.create_voice_delivery_receipt_rule(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceApi->create_voice_delivery_receipt_rule: #{e}"
end
```

#### Using the create_voice_delivery_receipt_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateVoiceDeliveryReceiptRule>, Integer, Hash)> create_voice_delivery_receipt_rule_with_http_info(opts)

```ruby
begin
  # Create Voice Delivery Receipt Rule
  data, status_code, headers = api_instance.create_voice_delivery_receipt_rule_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateVoiceDeliveryReceiptRule>
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceApi->create_voice_delivery_receipt_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **create_sms_delivery_receipt_rule_request** | [**CreateSmsDeliveryReceiptRuleRequest**](CreateSmsDeliveryReceiptRuleRequest.md) |  | [optional] |

### Return type

[**CreateVoiceDeliveryReceiptRule**](CreateVoiceDeliveryReceiptRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_voice_delivery_receipt_rule

> <DeleteVoiceDeliveryReceiptRule> delete_voice_delivery_receipt_rule(receipt_rule_id, opts)

Delete Voice Delivery Receipt Rule

_Delete voice delivery receipt automation_  Delete voice delivery receipt automation  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | receipt_rule_id | path | integer(int32) | true | Receipt rule id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::VoiceApi.new
receipt_rule_id = 'receipt_rule_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Delete Voice Delivery Receipt Rule
  result = api_instance.delete_voice_delivery_receipt_rule(receipt_rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceApi->delete_voice_delivery_receipt_rule: #{e}"
end
```

#### Using the delete_voice_delivery_receipt_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteVoiceDeliveryReceiptRule>, Integer, Hash)> delete_voice_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)

```ruby
begin
  # Delete Voice Delivery Receipt Rule
  data, status_code, headers = api_instance.delete_voice_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteVoiceDeliveryReceiptRule>
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceApi->delete_voice_delivery_receipt_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **receipt_rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**DeleteVoiceDeliveryReceiptRule**](DeleteVoiceDeliveryReceiptRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_voice_delivery_receipt_rule

> <UpdateVoiceDeliveryReceiptRule> update_voice_delivery_receipt_rule(receipt_rule_id, opts)

Update Voice Delivery Receipt Rule

_Update voice delivery receipt automation_  Update voice delivery receipt automation  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | receipt_rule_id | path | integer(int32) | true | Receipt rule id |  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | rule_name | string | true | none | Rule Name. | | match_type | number | true | none | Match Type. 0=All reports. | | action | string | true | none | Action to be taken (AUTO_REPLY, EMAIL_USER, EMAIL_FIXED, URL, SMS, POLL, GROUP_SMS, MOVE_CONTACT, CREATE_CONTACT, CREATE_CONTACT_PLUS_EMAIL, CREATE_CONTACT_PLUS_NAME_EMAIL CREATE_CONTACT_PLUS_NAME, SMPP, NONE). | | action_address | string | true | none | Action address. | | enabled | number | true | none | Enabled: Disabled=0 or Enabled=1. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::VoiceApi.new
receipt_rule_id = 'receipt_rule_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  create_sms_delivery_receipt_rule_request: ClickSend::CreateSmsDeliveryReceiptRuleRequest.new # CreateSmsDeliveryReceiptRuleRequest | 
}

begin
  # Update Voice Delivery Receipt Rule
  result = api_instance.update_voice_delivery_receipt_rule(receipt_rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceApi->update_voice_delivery_receipt_rule: #{e}"
end
```

#### Using the update_voice_delivery_receipt_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateVoiceDeliveryReceiptRule>, Integer, Hash)> update_voice_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)

```ruby
begin
  # Update Voice Delivery Receipt Rule
  data, status_code, headers = api_instance.update_voice_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateVoiceDeliveryReceiptRule>
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceApi->update_voice_delivery_receipt_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **receipt_rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **create_sms_delivery_receipt_rule_request** | [**CreateSmsDeliveryReceiptRuleRequest**](CreateSmsDeliveryReceiptRuleRequest.md) |  | [optional] |

### Return type

[**UpdateVoiceDeliveryReceiptRule**](UpdateVoiceDeliveryReceiptRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## view_voice_delivery_receipt_rule

> <ViewVoiceDeliveryReceiptRule> view_voice_delivery_receipt_rule(receipt_rule_id, opts)

View Voice Delivery Receipt Rule

_Get specific voice delivery receipt automation_  Get specific voice delivery receipt automation  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | receipt_rule_id | path | integer(int32) | true | Receipt rule id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::VoiceApi.new
receipt_rule_id = 'receipt_rule_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Voice Delivery Receipt Rule
  result = api_instance.view_voice_delivery_receipt_rule(receipt_rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceApi->view_voice_delivery_receipt_rule: #{e}"
end
```

#### Using the view_voice_delivery_receipt_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewVoiceDeliveryReceiptRule>, Integer, Hash)> view_voice_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)

```ruby
begin
  # View Voice Delivery Receipt Rule
  data, status_code, headers = api_instance.view_voice_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewVoiceDeliveryReceiptRule>
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceApi->view_voice_delivery_receipt_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **receipt_rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewVoiceDeliveryReceiptRule**](ViewVoiceDeliveryReceiptRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_voice_delivery_receipt_rules

> <ViewVoiceDeliveryReceiptRules> view_voice_delivery_receipt_rules(opts)

View Voice Delivery Receipt Rules

_Get all voice delivery receipt automations_  Get all voice delivery receipt automations  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | Page number | | limit | query | integer(int32) | false | Number of records per page |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::VoiceApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Voice Delivery Receipt Rules
  result = api_instance.view_voice_delivery_receipt_rules(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceApi->view_voice_delivery_receipt_rules: #{e}"
end
```

#### Using the view_voice_delivery_receipt_rules_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewVoiceDeliveryReceiptRules>, Integer, Hash)> view_voice_delivery_receipt_rules_with_http_info(opts)

```ruby
begin
  # View Voice Delivery Receipt Rules
  data, status_code, headers = api_instance.view_voice_delivery_receipt_rules_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewVoiceDeliveryReceiptRules>
rescue ClickSend::ApiError => e
  puts "Error when calling VoiceApi->view_voice_delivery_receipt_rules_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewVoiceDeliveryReceiptRules**](ViewVoiceDeliveryReceiptRules.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

