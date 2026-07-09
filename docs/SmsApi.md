# ClickSend::SmsApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**calculate_sms_price**](SmsApi.md#calculate_sms_price) | **POST** /v3/sms/price | Calculate SMS Price |
| [**cancel_all_sms**](SmsApi.md#cancel_all_sms) | **PUT** /v3/sms/cancel-all | Cancel All SMS |
| [**cancel_sms**](SmsApi.md#cancel_sms) | **PUT** /v3/sms/{message_id}/cancel | Cancel SMS |
| [**create_sms_delivery_receipt_rule**](SmsApi.md#create_sms_delivery_receipt_rule) | **POST** /v3/automations/sms/receipts | Create SMS Delivery Receipt Rule |
| [**create_sms_inbound_automation**](SmsApi.md#create_sms_inbound_automation) | **POST** /v3/automations/sms/inbound | Create SMS Inbound Automation |
| [**create_sms_template**](SmsApi.md#create_sms_template) | **POST** /v3/sms/templates | Create SMS Template |
| [**create_test_inbound_sms**](SmsApi.md#create_test_inbound_sms) | **POST** /v3/sms/inbound | Create Test Inbound SMS |
| [**create_test_sms_receipt**](SmsApi.md#create_test_sms_receipt) | **POST** /v3/sms/receipts | Create Test SMS Receipt |
| [**delete_sms_delivery_receipt_rule**](SmsApi.md#delete_sms_delivery_receipt_rule) | **DELETE** /v3/automations/sms/receipts/{receipt_rule_id} | Delete SMS Delivery Receipt Rule |
| [**delete_sms_inbound_automation**](SmsApi.md#delete_sms_inbound_automation) | **DELETE** /v3/automations/sms/inbound/{inbound_rule_id} | Delete SMS Inbound Automation |
| [**delete_sms_template**](SmsApi.md#delete_sms_template) | **DELETE** /v3/sms/templates/{template_id} | Delete SMS Template |
| [**export_sms_history**](SmsApi.md#export_sms_history) | **GET** /v3/sms/history/export | Export SMS History |
| [**mark_inbound_sms_as_read**](SmsApi.md#mark_inbound_sms_as_read) | **PUT** /v3/sms/inbound-read | Mark Inbound SMS as Read |
| [**mark_sms_receipt_as_read**](SmsApi.md#mark_sms_receipt_as_read) | **PUT** /v3/sms/receipts-read | Mark SMS Receipt As Read |
| [**mark_specific_inbound_sms_message_as_read**](SmsApi.md#mark_specific_inbound_sms_message_as_read) | **PUT** /v3/sms/inbound-read/{message_id} | Mark Specific Inbound SMS Message As Read |
| [**send_sms**](SmsApi.md#send_sms) | **POST** /v3/sms/send | Send SMS |
| [**update_sms_delivery_receipt_rule**](SmsApi.md#update_sms_delivery_receipt_rule) | **PUT** /v3/automations/sms/receipts/{receipt_rule_id} | Update SMS Delivery Receipt Rule |
| [**update_sms_inbound_automation**](SmsApi.md#update_sms_inbound_automation) | **PUT** /v3/automations/sms/inbound/{inbound_rule_id} | Update SMS Inbound Automation |
| [**update_sms_template**](SmsApi.md#update_sms_template) | **PUT** /v3/sms/templates/{template_id} | Update SMS Template |
| [**view_a_specific_inbound_sms_message**](SmsApi.md#view_a_specific_inbound_sms_message) | **GET** /v3/sms/inbound/{original_message_id} | View a specific inbound SMS message |
| [**view_a_specific_sms_template**](SmsApi.md#view_a_specific_sms_template) | **GET** /v3/sms/templates/{template_id} | View a Specific SMS Template |
| [**view_inbound_sms**](SmsApi.md#view_inbound_sms) | **GET** /v3/sms/inbound | View Inbound SMS |
| [**view_sms_delivery_receipt_rule**](SmsApi.md#view_sms_delivery_receipt_rule) | **GET** /v3/automations/sms/receipts/{receipt_rule_id} | View SMS Delivery Receipt Rule |
| [**view_sms_delivery_receipt_rules**](SmsApi.md#view_sms_delivery_receipt_rules) | **GET** /v3/automations/sms/receipts | View SMS Delivery Receipt Rules |
| [**view_sms_history**](SmsApi.md#view_sms_history) | **GET** /v3/sms/history | View SMS History |
| [**view_sms_inbound_automation**](SmsApi.md#view_sms_inbound_automation) | **GET** /v3/automations/sms/inbound/{inbound_rule_id} | View SMS Inbound Automation |
| [**view_sms_inbound_automations**](SmsApi.md#view_sms_inbound_automations) | **GET** /v3/automations/sms/inbound | View SMS Inbound Automations |
| [**view_sms_receipts**](SmsApi.md#view_sms_receipts) | **GET** /v3/sms/receipts | View SMS Receipts |
| [**view_sms_templates**](SmsApi.md#view_sms_templates) | **GET** /v3/sms/templates | View SMS Templates |
| [**view_specific_sms_receipt**](SmsApi.md#view_specific_sms_receipt) | **GET** /v3/sms/receipts/{message_id} | View Specific SMS Receipt |


## calculate_sms_price

> <CalculateSmsPrice> calculate_sms_price(opts)

Calculate SMS Price

Use this endpoint to calculate the price of sending messages. The cost of sending messages varies based on the <a href=\"https://help.clicksend.com/article/h474eseq3a-how-many-characters-can-i-send-in-an-sms\" target=\"_blank\">type</a> and length of the message.

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

api_instance = ClickSend::SmsApi.new
opts = {
  content_type: 'application/json', # String | 
  calculate_sms_price_request: ClickSend::CalculateSmsPriceRequest.new # CalculateSmsPriceRequest | 
}

begin
  # Calculate SMS Price
  result = api_instance.calculate_sms_price(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->calculate_sms_price: #{e}"
end
```

#### Using the calculate_sms_price_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalculateSmsPrice>, Integer, Hash)> calculate_sms_price_with_http_info(opts)

```ruby
begin
  # Calculate SMS Price
  data, status_code, headers = api_instance.calculate_sms_price_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalculateSmsPrice>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->calculate_sms_price_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **calculate_sms_price_request** | [**CalculateSmsPriceRequest**](CalculateSmsPriceRequest.md) |  | [optional] |

### Return type

[**CalculateSmsPrice**](CalculateSmsPrice.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## cancel_all_sms

> <CancelAllSms> cancel_all_sms(opts)

Cancel All SMS

Use this endpoint to cancel all scheduled SMS. To cancel only one scheduled SMS, use the **Cancel SMS** endpoint.

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

api_instance = ClickSend::SmsApi.new
opts = {
  content_type: 'application/json', # String | 
  cancel_all_sms_request: ClickSend::CancelAllSmsRequest.new # CancelAllSmsRequest | 
}

begin
  # Cancel All SMS
  result = api_instance.cancel_all_sms(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->cancel_all_sms: #{e}"
end
```

#### Using the cancel_all_sms_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CancelAllSms>, Integer, Hash)> cancel_all_sms_with_http_info(opts)

```ruby
begin
  # Cancel All SMS
  data, status_code, headers = api_instance.cancel_all_sms_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CancelAllSms>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->cancel_all_sms_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **cancel_all_sms_request** | [**CancelAllSmsRequest**](CancelAllSmsRequest.md) |  | [optional] |

### Return type

[**CancelAllSms**](CancelAllSms.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## cancel_sms

> <CancelSms> cancel_sms(message_id, opts)

Cancel SMS

Use this endpoint to cancel a specific scheduled SMS. Unlike the **Cancel All SMS** endpoint, which cancels all scheduled SMS, this endpoint only cancels one specified scheduled SMS.  Specify the scheduled SMS to cancel by providing its _message_id_.

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

api_instance = ClickSend::SmsApi.new
message_id = 'message_id_example' # String | The _message_id_ of the scheduled SMS to cancel.
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Cancel SMS
  result = api_instance.cancel_sms(message_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->cancel_sms: #{e}"
end
```

#### Using the cancel_sms_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CancelSms>, Integer, Hash)> cancel_sms_with_http_info(message_id, opts)

```ruby
begin
  # Cancel SMS
  data, status_code, headers = api_instance.cancel_sms_with_http_info(message_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CancelSms>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->cancel_sms_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** | The _message_id_ of the scheduled SMS to cancel. |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**CancelSms**](CancelSms.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## create_sms_delivery_receipt_rule

> <CreateSmsDeliveryReceiptRule> create_sms_delivery_receipt_rule(opts)

Create SMS Delivery Receipt Rule

_Create sms delivery receipt automations_  Create sms delivery receipt automations  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | rule_name | string | true | none | Rule Name. | | match_type | number | true | none | Match Type. 0=All reports. | | action | string | true | none | Action to be taken (AUTO_REPLY, EMAIL_USER, EMAIL_FIXED, URL, SMS, POLL, GROUP_SMS, MOVE_CONTACT, CREATE_CONTACT, CREATE_CONTACT_PLUS_EMAIL, CREATE_CONTACT_PLUS_NAME_EMAIL CREATE_CONTACT_PLUS_NAME, SMPP, NONE). | | action_address | string | true | none | Action address. | | enabled | number | true | none | Enabled: Disabled=0 or Enabled=1. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SmsApi.new
opts = {
  content_type: 'application/json', # String | 
  create_sms_delivery_receipt_rule_request: ClickSend::CreateSmsDeliveryReceiptRuleRequest.new # CreateSmsDeliveryReceiptRuleRequest | 
}

begin
  # Create SMS Delivery Receipt Rule
  result = api_instance.create_sms_delivery_receipt_rule(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->create_sms_delivery_receipt_rule: #{e}"
end
```

#### Using the create_sms_delivery_receipt_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateSmsDeliveryReceiptRule>, Integer, Hash)> create_sms_delivery_receipt_rule_with_http_info(opts)

```ruby
begin
  # Create SMS Delivery Receipt Rule
  data, status_code, headers = api_instance.create_sms_delivery_receipt_rule_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateSmsDeliveryReceiptRule>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->create_sms_delivery_receipt_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **create_sms_delivery_receipt_rule_request** | [**CreateSmsDeliveryReceiptRuleRequest**](CreateSmsDeliveryReceiptRuleRequest.md) |  | [optional] |

### Return type

[**CreateSmsDeliveryReceiptRule**](CreateSmsDeliveryReceiptRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_sms_inbound_automation

> <CreateSmsInboundAutomation> create_sms_inbound_automation(opts)

Create SMS Inbound Automation

_Create new inbound sms automation_  Create new inbound sms automation  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | dedicated_number | string | true | none | Decicated Number. Can be '\\*' to apply to all numbers. | | rule_name | string | true | none | Rule Name. | | message_search_type | number | true | none | Message Search Type: 0=Any message, 1=starts with, 2=contains, 3=does not contain. | | message_search_term | string | true | none | Message search term. | | action | string | true | none | Action to be taken (AUTO_REPLY, EMAIL_USER, EMAIL_FIXED, URL, SMS, POLL, GROUP_SMS, MOVE_CONTACT, CREATE_CONTACT, CREATE_CONTACT_PLUS_EMAIL, CREATE_CONTACT_PLUS_NAME_EMAIL CREATE_CONTACT_PLUS_NAME, SMPP, NONE). | | action_address | string | true | none | Action address. | | enabled | number | true | none | Enabled: Disabled=0 or Enabled=1. | | webhook_type | string | false | Required when action = URL only | Set as post, get, or json to change the format of the request sent. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SmsApi.new
opts = {
  content_type: 'application/json', # String | 
  create_sms_inbound_automation_request: ClickSend::CreateSmsInboundAutomationRequest.new # CreateSmsInboundAutomationRequest | 
}

begin
  # Create SMS Inbound Automation
  result = api_instance.create_sms_inbound_automation(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->create_sms_inbound_automation: #{e}"
end
```

#### Using the create_sms_inbound_automation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateSmsInboundAutomation>, Integer, Hash)> create_sms_inbound_automation_with_http_info(opts)

```ruby
begin
  # Create SMS Inbound Automation
  data, status_code, headers = api_instance.create_sms_inbound_automation_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateSmsInboundAutomation>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->create_sms_inbound_automation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **create_sms_inbound_automation_request** | [**CreateSmsInboundAutomationRequest**](CreateSmsInboundAutomationRequest.md) |  | [optional] |

### Return type

[**CreateSmsInboundAutomation**](CreateSmsInboundAutomation.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_sms_template

> <CreateSmsTemplate> create_sms_template(opts)

Create SMS Template

Use this endpoint to create a SMS template that you can use for sending SMS.

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

api_instance = ClickSend::SmsApi.new
opts = {
  content_type: 'application/json', # String | 
  create_sms_template_request: ClickSend::CreateSmsTemplateRequest.new # CreateSmsTemplateRequest | 
}

begin
  # Create SMS Template
  result = api_instance.create_sms_template(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->create_sms_template: #{e}"
end
```

#### Using the create_sms_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateSmsTemplate>, Integer, Hash)> create_sms_template_with_http_info(opts)

```ruby
begin
  # Create SMS Template
  data, status_code, headers = api_instance.create_sms_template_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateSmsTemplate>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->create_sms_template_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **create_sms_template_request** | [**CreateSmsTemplateRequest**](CreateSmsTemplateRequest.md) |  | [optional] |

### Return type

[**CreateSmsTemplate**](CreateSmsTemplate.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_test_inbound_sms

> <CreateTestInboundSms> create_test_inbound_sms(opts)

Create Test Inbound SMS

Use this endpoint to generate and send a test <a href=\"https://help.clicksend.com/article/ik4hw5xu35-can-i-receive-inbound-sms-to-my-url\" target=\"_blank\">inbound SMS</a> to your webhook URL. Inbound SMS are messages sent by your recipient to you.  This test endpoint allows you to verify that the inbound SMS is correctly sent to your webhook URL.

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

api_instance = ClickSend::SmsApi.new
opts = {
  content_type: 'application/json', # String | 
  create_test_inbound_sms_request: ClickSend::CreateTestInboundSmsRequest.new({url: 'url_example'}) # CreateTestInboundSmsRequest | 
}

begin
  # Create Test Inbound SMS
  result = api_instance.create_test_inbound_sms(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->create_test_inbound_sms: #{e}"
end
```

#### Using the create_test_inbound_sms_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateTestInboundSms>, Integer, Hash)> create_test_inbound_sms_with_http_info(opts)

```ruby
begin
  # Create Test Inbound SMS
  data, status_code, headers = api_instance.create_test_inbound_sms_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateTestInboundSms>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->create_test_inbound_sms_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **create_test_inbound_sms_request** | [**CreateTestInboundSmsRequest**](CreateTestInboundSmsRequest.md) |  | [optional] |

### Return type

[**CreateTestInboundSms**](CreateTestInboundSms.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_test_sms_receipt

> <CreateTestSmsReceipt> create_test_sms_receipt(opts)

Create Test SMS Receipt

Use this endpoint to generate and send a test <a href=\"https://help.clicksend.com/article/49eq1qdcui-how-do-i-receive-sms-delivery-receipts-delivery-status-updates\" target=\"_blank\">SMS delivery receipt</a> to your webhook URL. When you send an SMS, a delivery receipt is generated and can be received at your webhook URL. This test endpoint allows you to verify that the receipt is correctly sent to your webhook URL.  Additionally, you can obtain SMS receipts by setting the webhook URL to **poll** and periodically calling the **View SMS Receipt** endpoint to check for new receipts. This process is known as _polling_.

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

api_instance = ClickSend::SmsApi.new
opts = {
  content_type: 'application/json', # String | 
  create_test_sms_receipt_request: ClickSend::CreateTestSmsReceiptRequest.new({url: 'url_example'}) # CreateTestSmsReceiptRequest | 
}

begin
  # Create Test SMS Receipt
  result = api_instance.create_test_sms_receipt(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->create_test_sms_receipt: #{e}"
end
```

#### Using the create_test_sms_receipt_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateTestSmsReceipt>, Integer, Hash)> create_test_sms_receipt_with_http_info(opts)

```ruby
begin
  # Create Test SMS Receipt
  data, status_code, headers = api_instance.create_test_sms_receipt_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateTestSmsReceipt>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->create_test_sms_receipt_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **create_test_sms_receipt_request** | [**CreateTestSmsReceiptRequest**](CreateTestSmsReceiptRequest.md) |  | [optional] |

### Return type

[**CreateTestSmsReceipt**](CreateTestSmsReceipt.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_sms_delivery_receipt_rule

> <DeleteSmsDeliveryReceiptRule> delete_sms_delivery_receipt_rule(receipt_rule_id, opts)

Delete SMS Delivery Receipt Rule

_Delete sms delivery receipt automation_  Delete sms delivery receipt automation  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | receipt_rule_id | path | integer(int32) | true | Receipt rule id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SmsApi.new
receipt_rule_id = 'receipt_rule_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Delete SMS Delivery Receipt Rule
  result = api_instance.delete_sms_delivery_receipt_rule(receipt_rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->delete_sms_delivery_receipt_rule: #{e}"
end
```

#### Using the delete_sms_delivery_receipt_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteSmsDeliveryReceiptRule>, Integer, Hash)> delete_sms_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)

```ruby
begin
  # Delete SMS Delivery Receipt Rule
  data, status_code, headers = api_instance.delete_sms_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteSmsDeliveryReceiptRule>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->delete_sms_delivery_receipt_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **receipt_rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**DeleteSmsDeliveryReceiptRule**](DeleteSmsDeliveryReceiptRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_sms_inbound_automation

> <DeleteSmsInboundAutomation> delete_sms_inbound_automation(inbound_rule_id, opts)

Delete SMS Inbound Automation

_Delete inbound sms automation_  Delete inbound sms automation  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | inbound_rule_id | path | integer(int32) | true | Inbound rule id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SmsApi.new
inbound_rule_id = 'inbound_rule_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Delete SMS Inbound Automation
  result = api_instance.delete_sms_inbound_automation(inbound_rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->delete_sms_inbound_automation: #{e}"
end
```

#### Using the delete_sms_inbound_automation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteSmsInboundAutomation>, Integer, Hash)> delete_sms_inbound_automation_with_http_info(inbound_rule_id, opts)

```ruby
begin
  # Delete SMS Inbound Automation
  data, status_code, headers = api_instance.delete_sms_inbound_automation_with_http_info(inbound_rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteSmsInboundAutomation>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->delete_sms_inbound_automation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **inbound_rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**DeleteSmsInboundAutomation**](DeleteSmsInboundAutomation.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_sms_template

> <DeleteSmsTemplate> delete_sms_template(template_id, opts)

Delete SMS Template

Use this endpoint to delete a <a href=\"https://help.clicksend.com/article/9z9uloaz8y-sms-templates-for-different-industries\" target=\"_blank\">SMS template</a>. Specify the SMS template to delete by providing its _template_id_.

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

api_instance = ClickSend::SmsApi.new
template_id = 'template_id_example' # String | The ID of the template to delete.
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Delete SMS Template
  result = api_instance.delete_sms_template(template_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->delete_sms_template: #{e}"
end
```

#### Using the delete_sms_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteSmsTemplate>, Integer, Hash)> delete_sms_template_with_http_info(template_id, opts)

```ruby
begin
  # Delete SMS Template
  data, status_code, headers = api_instance.delete_sms_template_with_http_info(template_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteSmsTemplate>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->delete_sms_template_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **template_id** | **String** | The ID of the template to delete. |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**DeleteSmsTemplate**](DeleteSmsTemplate.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## export_sms_history

> <ExportSmsHistory> export_sms_history(opts)

Export SMS History

Use this endpoint to create a download link of your SMS history. You can filter the SMS history result using the query parameters.

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

api_instance = ClickSend::SmsApi.new
opts = {
  content_type: 'application/json', # String | 
  filename: 'filename_example', # String | The filename of the result. It should be in the .csv format.
  page: 1, # Integer | The page number to retrieve. Use this parameter to navigate through the [pagination](/#pagination) results. The default value is 1.
  limit: 15, # Integer | The number of items to return per page. This parameter controls the size of each page of results. The default value is 15.
  q: 'q_example', # String | Allows filtering of results based on your search criteria. The query should be in the format `field_name:value`.  1. **Field Name**: The field within the SMS history you want to filter by. You can use the following fields:          - _Status_: The status of the SMS. Available values for status are: Queued, Completed, Scheduled, WaitApproval, Failed, Cancelled, CancelledAfterReview, Received, Sent.              - _To_: The recipient of the SMS.              - _from_: The sender of the SMS.              - _subaccount_id_: The sub-account identifier.              - _message_id_: The ID of your SMS.          2. **Value**: The text or keyword you're searching for within the specified field. If left empty after the colon, the filter will look for all templates with any value in the **Field Name**.             For example, if you are searching for a SMS with the status of _Scheduled_, the final query would look like this:    `q=status:Scheduled`  <div class=\"info-box\">   <h4><i class=\"fas fa-info-circle\"></i> Note:</h4>   <div>   <p>Some characters have to be encoded. For example, if you are searching for SMS sent from the phone number +61437085284, your search query q would be:<br/></p>     <ul>       <li>q=from:%2B61437085284</li>     </ul>     <p>You can use the <a href=\"https://www.urlencoder.org/\" target=\"_blank\">URL encoder</a> to encode the text. If a character is not an alphanumeric character (A-Z, a-z, 0-9), it is typically either reserved or unsafe and should be encoded.</p>   </div> </div>
  order_by: 'order_by_example', # String | Specifies the field and order to sort the results by. The value is composed of the field name followed by a colon and the sort direction (asc for ascending or desc for descending).  The default sort order is by date in ascending order. You can use the following fields:    - _date_    - _username_   - _from_    - _to_   - _status_    - _body_  For example, if you want to order by the most recently sent SMS, you should sort by date in descending order. The query would look like this:    `order_by=date:desc`
  date_from: 56, # Integer | Start date to filter results. It should be in <a href=\"http://help.clicksend.com/what-is-a-unix-timestamp\" target=\"_blank\">Unix format</a>.
  date_to: 56 # Integer | End date to filter results. It should be in <a href=\"http://help.clicksend.com/what-is-a-unix-timestamp\" target=\"_blank\">Unix format</a>.
}

begin
  # Export SMS History
  result = api_instance.export_sms_history(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->export_sms_history: #{e}"
end
```

#### Using the export_sms_history_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ExportSmsHistory>, Integer, Hash)> export_sms_history_with_http_info(opts)

```ruby
begin
  # Export SMS History
  data, status_code, headers = api_instance.export_sms_history_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ExportSmsHistory>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->export_sms_history_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **filename** | **String** | The filename of the result. It should be in the .csv format. | [optional][default to &#39;export.csv&#39;] |
| **page** | **Integer** | The page number to retrieve. Use this parameter to navigate through the [pagination](/#pagination) results. The default value is 1. | [optional][default to 1] |
| **limit** | **Integer** | The number of items to return per page. This parameter controls the size of each page of results. The default value is 15. | [optional][default to 15] |
| **q** | **String** | Allows filtering of results based on your search criteria. The query should be in the format &#x60;field_name:value&#x60;.  1. **Field Name**: The field within the SMS history you want to filter by. You can use the following fields:          - _Status_: The status of the SMS. Available values for status are: Queued, Completed, Scheduled, WaitApproval, Failed, Cancelled, CancelledAfterReview, Received, Sent.              - _To_: The recipient of the SMS.              - _from_: The sender of the SMS.              - _subaccount_id_: The sub-account identifier.              - _message_id_: The ID of your SMS.          2. **Value**: The text or keyword you&#39;re searching for within the specified field. If left empty after the colon, the filter will look for all templates with any value in the **Field Name**.             For example, if you are searching for a SMS with the status of _Scheduled_, the final query would look like this:    &#x60;q&#x3D;status:Scheduled&#x60;  &lt;div class&#x3D;\&quot;info-box\&quot;&gt;   &lt;h4&gt;&lt;i class&#x3D;\&quot;fas fa-info-circle\&quot;&gt;&lt;/i&gt; Note:&lt;/h4&gt;   &lt;div&gt;   &lt;p&gt;Some characters have to be encoded. For example, if you are searching for SMS sent from the phone number +61437085284, your search query q would be:&lt;br/&gt;&lt;/p&gt;     &lt;ul&gt;       &lt;li&gt;q&#x3D;from:%2B61437085284&lt;/li&gt;     &lt;/ul&gt;     &lt;p&gt;You can use the &lt;a href&#x3D;\&quot;https://www.urlencoder.org/\&quot; target&#x3D;\&quot;_blank\&quot;&gt;URL encoder&lt;/a&gt; to encode the text. If a character is not an alphanumeric character (A-Z, a-z, 0-9), it is typically either reserved or unsafe and should be encoded.&lt;/p&gt;   &lt;/div&gt; &lt;/div&gt; | [optional][default to &#39;field_name&#39;] |
| **order_by** | **String** | Specifies the field and order to sort the results by. The value is composed of the field name followed by a colon and the sort direction (asc for ascending or desc for descending).  The default sort order is by date in ascending order. You can use the following fields:    - _date_    - _username_   - _from_    - _to_   - _status_    - _body_  For example, if you want to order by the most recently sent SMS, you should sort by date in descending order. The query would look like this:    &#x60;order_by&#x3D;date:desc&#x60; | [optional][default to &#39;date:asc&#39;] |
| **date_from** | **Integer** | Start date to filter results. It should be in &lt;a href&#x3D;\&quot;http://help.clicksend.com/what-is-a-unix-timestamp\&quot; target&#x3D;\&quot;_blank\&quot;&gt;Unix format&lt;/a&gt;. | [optional] |
| **date_to** | **Integer** | End date to filter results. It should be in &lt;a href&#x3D;\&quot;http://help.clicksend.com/what-is-a-unix-timestamp\&quot; target&#x3D;\&quot;_blank\&quot;&gt;Unix format&lt;/a&gt;. | [optional] |

### Return type

[**ExportSmsHistory**](ExportSmsHistory.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## mark_inbound_sms_as_read

> <MarkInboundSmsAsRead> mark_inbound_sms_as_read(opts)

Mark Inbound SMS as Read

Use this endpoint to mark all <a href=\"https://help.clicksend.com/article/ik4hw5xu35-can-i-receive-inbound-sms-to-my-url\" target=\"_blank\">inbound SMS</a> as read. Inbound SMS that has been marked as read won’t be shown in the **View Inbound SMS** endpoint. You can still use the **View Specific Inbound SMS** endpoint to view inbound SMS marked as read.  In the request, you can optionally add a _date_before_ parameter to only mark inbound SMS sent before that date as read.

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

api_instance = ClickSend::SmsApi.new
opts = {
  content_type: 'application/json', # String | 
  mark_sms_receipt_as_read_request: ClickSend::MarkSmsReceiptAsReadRequest.new # MarkSmsReceiptAsReadRequest | 
}

begin
  # Mark Inbound SMS as Read
  result = api_instance.mark_inbound_sms_as_read(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->mark_inbound_sms_as_read: #{e}"
end
```

#### Using the mark_inbound_sms_as_read_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MarkInboundSmsAsRead>, Integer, Hash)> mark_inbound_sms_as_read_with_http_info(opts)

```ruby
begin
  # Mark Inbound SMS as Read
  data, status_code, headers = api_instance.mark_inbound_sms_as_read_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MarkInboundSmsAsRead>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->mark_inbound_sms_as_read_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **mark_sms_receipt_as_read_request** | [**MarkSmsReceiptAsReadRequest**](MarkSmsReceiptAsReadRequest.md) |  | [optional] |

### Return type

[**MarkInboundSmsAsRead**](MarkInboundSmsAsRead.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## mark_sms_receipt_as_read

> <MarkSmsReceiptAsRead> mark_sms_receipt_as_read(opts)

Mark SMS Receipt As Read

Use this endpoint to mark all <a target=\"_blank\" href=\"https://help.clicksend.com/article/49eq1qdcui-how-do-i-receive-sms-delivery-receipts-delivery-status-updates\">SMS delivery receipts</a> as read. Delivery receipts that have been marked as read won’t be shown in the **View SMS Receipts** endpoint.  You can still use the **View Specific SMS Receipt** endpoint to view delivery receipts marked as read. In the request, you can optionally add a _date_before_ parameter to only mark receipts sent before that date as read

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

api_instance = ClickSend::SmsApi.new
opts = {
  content_type: 'application/json', # String | 
  mark_sms_receipt_as_read_request: ClickSend::MarkSmsReceiptAsReadRequest.new # MarkSmsReceiptAsReadRequest | 
}

begin
  # Mark SMS Receipt As Read
  result = api_instance.mark_sms_receipt_as_read(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->mark_sms_receipt_as_read: #{e}"
end
```

#### Using the mark_sms_receipt_as_read_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MarkSmsReceiptAsRead>, Integer, Hash)> mark_sms_receipt_as_read_with_http_info(opts)

```ruby
begin
  # Mark SMS Receipt As Read
  data, status_code, headers = api_instance.mark_sms_receipt_as_read_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MarkSmsReceiptAsRead>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->mark_sms_receipt_as_read_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **mark_sms_receipt_as_read_request** | [**MarkSmsReceiptAsReadRequest**](MarkSmsReceiptAsReadRequest.md) |  | [optional] |

### Return type

[**MarkSmsReceiptAsRead**](MarkSmsReceiptAsRead.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## mark_specific_inbound_sms_message_as_read

> <MarkSpecificInboundSmsMessageAsRead> mark_specific_inbound_sms_message_as_read(message_id, opts)

Mark Specific Inbound SMS Message As Read

Use this endpoint to mark a specific <a href=\"https://help.clicksend.com/article/ik4hw5xu35-can-i-receive-inbound-sms-to-my-url\" target=\"_blank\">inbound SMS</a> as read. Unlike the **View Inbound SMS** endpoint, which marks all inbound SMS as read,  this endpoint only marks one specified inbound SMS. Specify the SMS to be marked as read by providing its _message_id_.

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

api_instance = ClickSend::SmsApi.new
message_id = 'message_id_example' # String | The message_id of the inbound SMS to mark as read.  <div class=\"info-box\">   <h4><i class=\"fas fa-info-circle\"></i> Note:</h4>   <p>     When you receive an inbound message, you will get two parameters: <em>original_message_id</em> and <em>message_id</em>:   </p>   <ul>     <li><em>original_message_id</em>: This is the ID of the outbound message sent to the recipient</li>     <li><em>message_id</em>: This is the ID of the inbound message sent by the recipient.</li>   </ul> </div>
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Mark Specific Inbound SMS Message As Read
  result = api_instance.mark_specific_inbound_sms_message_as_read(message_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->mark_specific_inbound_sms_message_as_read: #{e}"
end
```

#### Using the mark_specific_inbound_sms_message_as_read_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MarkSpecificInboundSmsMessageAsRead>, Integer, Hash)> mark_specific_inbound_sms_message_as_read_with_http_info(message_id, opts)

```ruby
begin
  # Mark Specific Inbound SMS Message As Read
  data, status_code, headers = api_instance.mark_specific_inbound_sms_message_as_read_with_http_info(message_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MarkSpecificInboundSmsMessageAsRead>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->mark_specific_inbound_sms_message_as_read_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** | The message_id of the inbound SMS to mark as read.  &lt;div class&#x3D;\&quot;info-box\&quot;&gt;   &lt;h4&gt;&lt;i class&#x3D;\&quot;fas fa-info-circle\&quot;&gt;&lt;/i&gt; Note:&lt;/h4&gt;   &lt;p&gt;     When you receive an inbound message, you will get two parameters: &lt;em&gt;original_message_id&lt;/em&gt; and &lt;em&gt;message_id&lt;/em&gt;:   &lt;/p&gt;   &lt;ul&gt;     &lt;li&gt;&lt;em&gt;original_message_id&lt;/em&gt;: This is the ID of the outbound message sent to the recipient&lt;/li&gt;     &lt;li&gt;&lt;em&gt;message_id&lt;/em&gt;: This is the ID of the inbound message sent by the recipient.&lt;/li&gt;   &lt;/ul&gt; &lt;/div&gt; |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**MarkSpecificInboundSmsMessageAsRead**](MarkSpecificInboundSmsMessageAsRead.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## send_sms

> <SendSms> send_sms(opts)

Send SMS

Use this endpoint to send messages to your recipients, either as phone numbers or contacts from your contact list.  The sender of the message (<a href=\"https://help.clicksend.com/article/4kgj7krx00-what-is-a-sender-id-or-sender-number\" target=\"_blank\"><strong>Sender ID</strong></a>) can be a shared number, a dedicated number, alpha tag (business name), or your own number.  You can send messages both locally and globally, subject to the country restrictions. The cost of sending messages varies based on the <a href=\"https://help.clicksend.com/article/h474eseq3a-how-many-characters-can-i-send-in-an-sms\" target=\"_blank\">type</a> and length of the message.

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

api_instance = ClickSend::SmsApi.new
opts = {
  content_type: 'application/json', # String | 
  send_sms_request: ClickSend::SendSmsRequest.new # SendSmsRequest | 
}

begin
  # Send SMS
  result = api_instance.send_sms(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->send_sms: #{e}"
end
```

#### Using the send_sms_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendSms>, Integer, Hash)> send_sms_with_http_info(opts)

```ruby
begin
  # Send SMS
  data, status_code, headers = api_instance.send_sms_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendSms>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->send_sms_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **send_sms_request** | [**SendSmsRequest**](SendSmsRequest.md) |  | [optional] |

### Return type

[**SendSms**](SendSms.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_sms_delivery_receipt_rule

> <UpdateSmsDeliveryReceiptRule> update_sms_delivery_receipt_rule(receipt_rule_id, opts)

Update SMS Delivery Receipt Rule

_Update sms delivery receipt automation_  Update sms delivery receipt automation  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | receipt_rule_id | path | integer(int32) | true | Receipt rule id |  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | rule_name | string | true | none | Rule Name. | | match_type | number | true | none | Match Type. 0=All reports. | | action | string | true | none | Action to be taken (AUTO_REPLY, EMAIL_USER, EMAIL_FIXED, URL, SMS, POLL, GROUP_SMS, MOVE_CONTACT, CREATE_CONTACT, CREATE_CONTACT_PLUS_EMAIL, CREATE_CONTACT_PLUS_NAME_EMAIL CREATE_CONTACT_PLUS_NAME, SMPP, NONE). | | action_address | string | true | none | Action address. | | enabled | number | true | none | Enabled: Disabled=0 or Enabled=1. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SmsApi.new
receipt_rule_id = 'receipt_rule_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  create_sms_delivery_receipt_rule_request: ClickSend::CreateSmsDeliveryReceiptRuleRequest.new # CreateSmsDeliveryReceiptRuleRequest | 
}

begin
  # Update SMS Delivery Receipt Rule
  result = api_instance.update_sms_delivery_receipt_rule(receipt_rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->update_sms_delivery_receipt_rule: #{e}"
end
```

#### Using the update_sms_delivery_receipt_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateSmsDeliveryReceiptRule>, Integer, Hash)> update_sms_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)

```ruby
begin
  # Update SMS Delivery Receipt Rule
  data, status_code, headers = api_instance.update_sms_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateSmsDeliveryReceiptRule>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->update_sms_delivery_receipt_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **receipt_rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **create_sms_delivery_receipt_rule_request** | [**CreateSmsDeliveryReceiptRuleRequest**](CreateSmsDeliveryReceiptRuleRequest.md) |  | [optional] |

### Return type

[**UpdateSmsDeliveryReceiptRule**](UpdateSmsDeliveryReceiptRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_sms_inbound_automation

> <UpdateSmsInboundAutomation> update_sms_inbound_automation(inbound_rule_id, opts)

Update SMS Inbound Automation

_Update inbound sms automation_  Update inbound sms automation  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | inbound_rule_id | path | integer(int32) | true | Inbound rule id |  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | dedicated_number | string | true | none | Dedicated Number. Can be '\\*' to apply to all numbers. | | rule_name | string | true | none | Rule Name. | | message_search_type | number | true | none | Message Search Type: 0=Any message, 1=starts with, 2=contains, 3=does not contain. | | message_search_term | string | true | none | Message search term. | | action | string | true | none | Action to be taken (AUTO_REPLY, EMAIL_USER, EMAIL_FIXED, URL, SMS, POLL, GROUP_SMS, MOVE_CONTACT, CREATE_CONTACT, CREATE_CONTACT_PLUS_EMAIL, CREATE_CONTACT_PLUS_NAME_EMAIL CREATE_CONTACT_PLUS_NAME, SMPP, NONE). | | action_address | string | true | none | Action address. | | enabled | number | true | none | Enabled: Disabled=0 or Enabled=1. | | webhook_type | string | false | Required when action = URL only | Set as post, get, or json to change the format of the request sent. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SmsApi.new
inbound_rule_id = 'inbound_rule_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  update_sms_inbound_automation_request: ClickSend::UpdateSmsInboundAutomationRequest.new # UpdateSmsInboundAutomationRequest | 
}

begin
  # Update SMS Inbound Automation
  result = api_instance.update_sms_inbound_automation(inbound_rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->update_sms_inbound_automation: #{e}"
end
```

#### Using the update_sms_inbound_automation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateSmsInboundAutomation>, Integer, Hash)> update_sms_inbound_automation_with_http_info(inbound_rule_id, opts)

```ruby
begin
  # Update SMS Inbound Automation
  data, status_code, headers = api_instance.update_sms_inbound_automation_with_http_info(inbound_rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateSmsInboundAutomation>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->update_sms_inbound_automation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **inbound_rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **update_sms_inbound_automation_request** | [**UpdateSmsInboundAutomationRequest**](UpdateSmsInboundAutomationRequest.md) |  | [optional] |

### Return type

[**UpdateSmsInboundAutomation**](UpdateSmsInboundAutomation.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_sms_template

> <UpdateSmsTemplate> update_sms_template(template_id, opts)

Update SMS Template

Use this endpoint to update a <a href=\"https://help.clicksend.com/article/9z9uloaz8y-sms-templates-for-different-industries\" target=\"_blank\">SMS template</a>.

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

api_instance = ClickSend::SmsApi.new
template_id = 'template_id_example' # String | The ID of the template to update.
opts = {
  content_type: 'application/json', # String | 
  create_sms_template_request: ClickSend::CreateSmsTemplateRequest.new # CreateSmsTemplateRequest | 
}

begin
  # Update SMS Template
  result = api_instance.update_sms_template(template_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->update_sms_template: #{e}"
end
```

#### Using the update_sms_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateSmsTemplate>, Integer, Hash)> update_sms_template_with_http_info(template_id, opts)

```ruby
begin
  # Update SMS Template
  data, status_code, headers = api_instance.update_sms_template_with_http_info(template_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateSmsTemplate>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->update_sms_template_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **template_id** | **String** | The ID of the template to update. |  |
| **content_type** | **String** |  | [optional] |
| **create_sms_template_request** | [**CreateSmsTemplateRequest**](CreateSmsTemplateRequest.md) |  | [optional] |

### Return type

[**UpdateSmsTemplate**](UpdateSmsTemplate.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## view_a_specific_inbound_sms_message

> <ViewASpecificInboundSmsMessage> view_a_specific_inbound_sms_message(original_message_id, opts)

View a specific inbound SMS message

Use this endpoint to retrieve a specific inbound SMS, including those that have been marked as read.  Inbound SMS are messages sent by your recipient to you. This endpoint enables you to retrieve those inbound SMS.

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

api_instance = ClickSend::SmsApi.new
original_message_id = 'original_message_id_example' # String | The _original_message_id_ of the inbound SMS to view. If the recipient replied with multiple messages, this endpoint returns the first inbound SMS received.  <div class=\"info-box\">   <h4><i class=\"fas fa-info-circle\"></i> Note:</h4>   <p>     When you receive an inbound message, you will get two parameters: <em>original_message_id</em> and <em>message_id</em>:   </p>   <ul>     <li><em>original_message_id</em>: This is the ID of the outbound message sent to the recipient</li>     <li><em>message_id</em>: This is the ID of the inbound message sent by the recipient.</li>   </ul> </div>
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View a specific inbound SMS message
  result = api_instance.view_a_specific_inbound_sms_message(original_message_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_a_specific_inbound_sms_message: #{e}"
end
```

#### Using the view_a_specific_inbound_sms_message_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewASpecificInboundSmsMessage>, Integer, Hash)> view_a_specific_inbound_sms_message_with_http_info(original_message_id, opts)

```ruby
begin
  # View a specific inbound SMS message
  data, status_code, headers = api_instance.view_a_specific_inbound_sms_message_with_http_info(original_message_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewASpecificInboundSmsMessage>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_a_specific_inbound_sms_message_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **original_message_id** | **String** | The _original_message_id_ of the inbound SMS to view. If the recipient replied with multiple messages, this endpoint returns the first inbound SMS received.  &lt;div class&#x3D;\&quot;info-box\&quot;&gt;   &lt;h4&gt;&lt;i class&#x3D;\&quot;fas fa-info-circle\&quot;&gt;&lt;/i&gt; Note:&lt;/h4&gt;   &lt;p&gt;     When you receive an inbound message, you will get two parameters: &lt;em&gt;original_message_id&lt;/em&gt; and &lt;em&gt;message_id&lt;/em&gt;:   &lt;/p&gt;   &lt;ul&gt;     &lt;li&gt;&lt;em&gt;original_message_id&lt;/em&gt;: This is the ID of the outbound message sent to the recipient&lt;/li&gt;     &lt;li&gt;&lt;em&gt;message_id&lt;/em&gt;: This is the ID of the inbound message sent by the recipient.&lt;/li&gt;   &lt;/ul&gt; &lt;/div&gt; |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewASpecificInboundSmsMessage**](ViewASpecificInboundSmsMessage.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_a_specific_sms_template

> <ViewASpecificSmsTemplate> view_a_specific_sms_template(template_id, opts)

View a Specific SMS Template

Use this endpoint to retrieve a <a href=\"https://help.clicksend.com/article/9z9uloaz8y-sms-templates-for-different-industries\" target=\"_blank\">SMS template</a>. Specify which template to retrieve using the template ID.

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

api_instance = ClickSend::SmsApi.new
template_id = 'template_id_example' # String | The ID of the template to retrieve
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View a Specific SMS Template
  result = api_instance.view_a_specific_sms_template(template_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_a_specific_sms_template: #{e}"
end
```

#### Using the view_a_specific_sms_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewASpecificSmsTemplate>, Integer, Hash)> view_a_specific_sms_template_with_http_info(template_id, opts)

```ruby
begin
  # View a Specific SMS Template
  data, status_code, headers = api_instance.view_a_specific_sms_template_with_http_info(template_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewASpecificSmsTemplate>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_a_specific_sms_template_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **template_id** | **String** | The ID of the template to retrieve |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewASpecificSmsTemplate**](ViewASpecificSmsTemplate.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_inbound_sms

> <ViewInboundSms> view_inbound_sms(opts)

View Inbound SMS

Use this endpoint to retrieve <a href=\"https://help.clicksend.com/article/49eq1qdcui-how-do-i-receive-sms-delivery-receipts-delivery-status-updates\" target=\"_blank\">SMS delivery receipts</a> sent by your recipient.  To be able to view receipts, add a <a href=\"https://help.clicksend.com/article/ut4ttdrrai-incoming-reply-sms-options\">inbound rule</a> with the Action set to **POLL** in the Dashboard, or use the [**Create SMS Inbound Automation**](/automations/sms/other/create-sms-inbound-automation) endpoint.  Control [pagination](/#pagination) with the _page_ and _limit_ query parameters to specify the page of results and the number of items returned.  <div class=\"info-box\">   <h4><i class=\"fas fa-info-circle\"></i> Note:</h4>   <p>If you have multiple inbound rules set to <strong>POLL</strong>, you will receive the inbound message multiple times.</p> </div>

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

api_instance = ClickSend::SmsApi.new
opts = {
  content_type: 'application/json', # String | 
  page: 1, # Integer | The page number to retrieve. Use this parameter to navigate through the [pagination](/#pagination) results. The default value is 1.
  limit: 15 # Integer | The number of items to return per page. This parameter controls the size of each page of results. The default value is 15.
}

begin
  # View Inbound SMS
  result = api_instance.view_inbound_sms(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_inbound_sms: #{e}"
end
```

#### Using the view_inbound_sms_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewInboundSms>, Integer, Hash)> view_inbound_sms_with_http_info(opts)

```ruby
begin
  # View Inbound SMS
  data, status_code, headers = api_instance.view_inbound_sms_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewInboundSms>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_inbound_sms_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **page** | **Integer** | The page number to retrieve. Use this parameter to navigate through the [pagination](/#pagination) results. The default value is 1. | [optional][default to 1] |
| **limit** | **Integer** | The number of items to return per page. This parameter controls the size of each page of results. The default value is 15. | [optional][default to 15] |

### Return type

[**ViewInboundSms**](ViewInboundSms.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_sms_delivery_receipt_rule

> <ViewSmsDeliveryReceiptRule> view_sms_delivery_receipt_rule(receipt_rule_id, opts)

View SMS Delivery Receipt Rule

_Get specific sms delivery receipt automation_  Get specific sms delivery receipt automation  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | receipt_rule_id | path | integer(int32) | true | Receipt rule id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SmsApi.new
receipt_rule_id = 'receipt_rule_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View SMS Delivery Receipt Rule
  result = api_instance.view_sms_delivery_receipt_rule(receipt_rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_sms_delivery_receipt_rule: #{e}"
end
```

#### Using the view_sms_delivery_receipt_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewSmsDeliveryReceiptRule>, Integer, Hash)> view_sms_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)

```ruby
begin
  # View SMS Delivery Receipt Rule
  data, status_code, headers = api_instance.view_sms_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewSmsDeliveryReceiptRule>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_sms_delivery_receipt_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **receipt_rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewSmsDeliveryReceiptRule**](ViewSmsDeliveryReceiptRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_sms_delivery_receipt_rules

> <ViewSmsDeliveryReceiptRules> view_sms_delivery_receipt_rules(opts)

View SMS Delivery Receipt Rules

_Get all sms delivery receipt automations_  Get all sms delivery receipt automations  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | Page number | | limit | query | integer(int32) | false | Number of records per page |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SmsApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View SMS Delivery Receipt Rules
  result = api_instance.view_sms_delivery_receipt_rules(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_sms_delivery_receipt_rules: #{e}"
end
```

#### Using the view_sms_delivery_receipt_rules_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewSmsDeliveryReceiptRules>, Integer, Hash)> view_sms_delivery_receipt_rules_with_http_info(opts)

```ruby
begin
  # View SMS Delivery Receipt Rules
  data, status_code, headers = api_instance.view_sms_delivery_receipt_rules_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewSmsDeliveryReceiptRules>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_sms_delivery_receipt_rules_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewSmsDeliveryReceiptRules**](ViewSmsDeliveryReceiptRules.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_sms_history

> <ViewSmsHistory> view_sms_history(opts)

View SMS History

Use this endpoint to view previously sent SMS. You can filter the SMS history result using the query parameters.

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

api_instance = ClickSend::SmsApi.new
opts = {
  content_type: 'application/json', # String | 
  page: 1, # Integer | The page number to retrieve. Use this parameter to navigate through the [pagination](/#pagination) results. The default value is 1.
  limit: 15, # Integer | The number of items to return per page. This parameter controls the size of each page of results. The default value is 15.
  q: 'q_example', # String | Allows filtering of results based on your search criteria. The query should be in the format `field_name:value`.  1. **Field Name**: The field within the SMS history you want to filter by. You can use the following fields:          - _Status_: The status of the SMS. Available values for status are: Queued, Completed, Scheduled, WaitApproval, Failed, Cancelled, CancelledAfterReview, Received, Sent.              - _To_: The recipient of the SMS.              - _from_: The sender of the SMS.              - _subaccount_id_: The sub-account identifier.              - _message_id_: The ID of your SMS.          2. **Value**: The text or keyword you're searching for within the specified field. If left empty after the colon, the filter will look for all templates with any value in the **Field Name**.             For example, if you are searching for a SMS with the status of Scheduled, the final query would look like this:    `q=status:Scheduled`  <div class=\"info-box\">   <h4><i class=\"fas fa-info-circle\"></i> Note:</h4>   <div>    <p>Some characters have to be encoded. For example, if you are searching for SMS sent from the phone number +61437085284, your search query q would be:<br/></p>     <ul>       <li>q=from:%2B61437085284</li>     </ul>     <p>You can use the <a href=\"https://www.urlencoder.org/\" target=\"_blank\">URL encoder</a> to encode the text. If a character is not an alphanumeric character (A-Z, a-z, 0-9), it is typically either reserved or unsafe and should be encoded.</p>   </div> </div>
  order_by: 'order_by_example', # String | Specifies the field and order to sort the results by. The value is composed of the field name followed by a colon and the sort direction (_asc_ for ascending or _desc_ for descending).  The default sort order is by _date_ in ascending order. You can use the following fields:    - _date_   - _username_   - _from_    - _to_   - _status_   - _body_  For example, if you want to order by the most recently sent SMS, you should sort by date in descending order. The query would look like this:    `order_by=date:desc`
  date_from: 56, # Integer | Start date to filter results. It should be in <a href=\"http://help.clicksend.com/what-is-a-unix-timestamp\" target=\"_blank\">Unix format</a>.
  date_to: 56 # Integer | End date to filter results. It should be in <a href=\"http://help.clicksend.com/what-is-a-unix-timestamp\" target=\"_blank\">Unix format</a>.
}

begin
  # View SMS History
  result = api_instance.view_sms_history(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_sms_history: #{e}"
end
```

#### Using the view_sms_history_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewSmsHistory>, Integer, Hash)> view_sms_history_with_http_info(opts)

```ruby
begin
  # View SMS History
  data, status_code, headers = api_instance.view_sms_history_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewSmsHistory>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_sms_history_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **page** | **Integer** | The page number to retrieve. Use this parameter to navigate through the [pagination](/#pagination) results. The default value is 1. | [optional][default to 1] |
| **limit** | **Integer** | The number of items to return per page. This parameter controls the size of each page of results. The default value is 15. | [optional][default to 15] |
| **q** | **String** | Allows filtering of results based on your search criteria. The query should be in the format &#x60;field_name:value&#x60;.  1. **Field Name**: The field within the SMS history you want to filter by. You can use the following fields:          - _Status_: The status of the SMS. Available values for status are: Queued, Completed, Scheduled, WaitApproval, Failed, Cancelled, CancelledAfterReview, Received, Sent.              - _To_: The recipient of the SMS.              - _from_: The sender of the SMS.              - _subaccount_id_: The sub-account identifier.              - _message_id_: The ID of your SMS.          2. **Value**: The text or keyword you&#39;re searching for within the specified field. If left empty after the colon, the filter will look for all templates with any value in the **Field Name**.             For example, if you are searching for a SMS with the status of Scheduled, the final query would look like this:    &#x60;q&#x3D;status:Scheduled&#x60;  &lt;div class&#x3D;\&quot;info-box\&quot;&gt;   &lt;h4&gt;&lt;i class&#x3D;\&quot;fas fa-info-circle\&quot;&gt;&lt;/i&gt; Note:&lt;/h4&gt;   &lt;div&gt;    &lt;p&gt;Some characters have to be encoded. For example, if you are searching for SMS sent from the phone number +61437085284, your search query q would be:&lt;br/&gt;&lt;/p&gt;     &lt;ul&gt;       &lt;li&gt;q&#x3D;from:%2B61437085284&lt;/li&gt;     &lt;/ul&gt;     &lt;p&gt;You can use the &lt;a href&#x3D;\&quot;https://www.urlencoder.org/\&quot; target&#x3D;\&quot;_blank\&quot;&gt;URL encoder&lt;/a&gt; to encode the text. If a character is not an alphanumeric character (A-Z, a-z, 0-9), it is typically either reserved or unsafe and should be encoded.&lt;/p&gt;   &lt;/div&gt; &lt;/div&gt; | [optional][default to &#39;field_name&#39;] |
| **order_by** | **String** | Specifies the field and order to sort the results by. The value is composed of the field name followed by a colon and the sort direction (_asc_ for ascending or _desc_ for descending).  The default sort order is by _date_ in ascending order. You can use the following fields:    - _date_   - _username_   - _from_    - _to_   - _status_   - _body_  For example, if you want to order by the most recently sent SMS, you should sort by date in descending order. The query would look like this:    &#x60;order_by&#x3D;date:desc&#x60; | [optional][default to &#39;date:asc&#39;] |
| **date_from** | **Integer** | Start date to filter results. It should be in &lt;a href&#x3D;\&quot;http://help.clicksend.com/what-is-a-unix-timestamp\&quot; target&#x3D;\&quot;_blank\&quot;&gt;Unix format&lt;/a&gt;. | [optional] |
| **date_to** | **Integer** | End date to filter results. It should be in &lt;a href&#x3D;\&quot;http://help.clicksend.com/what-is-a-unix-timestamp\&quot; target&#x3D;\&quot;_blank\&quot;&gt;Unix format&lt;/a&gt;. | [optional] |

### Return type

[**ViewSmsHistory**](ViewSmsHistory.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_sms_inbound_automation

> <ViewSmsInboundAutomation> view_sms_inbound_automation(inbound_rule_id, opts)

View SMS Inbound Automation

_Get specific inbound sms automation_  Get specific inbound sms automation  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | inbound_rule_id | path | integer(int32) | true | Inbound rule id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SmsApi.new
inbound_rule_id = 'inbound_rule_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View SMS Inbound Automation
  result = api_instance.view_sms_inbound_automation(inbound_rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_sms_inbound_automation: #{e}"
end
```

#### Using the view_sms_inbound_automation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewSmsInboundAutomation>, Integer, Hash)> view_sms_inbound_automation_with_http_info(inbound_rule_id, opts)

```ruby
begin
  # View SMS Inbound Automation
  data, status_code, headers = api_instance.view_sms_inbound_automation_with_http_info(inbound_rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewSmsInboundAutomation>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_sms_inbound_automation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **inbound_rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewSmsInboundAutomation**](ViewSmsInboundAutomation.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_sms_inbound_automations

> <ViewSmsInboundAutomations> view_sms_inbound_automations(opts)

View SMS Inbound Automations

_Get all inbound sms automations_  Get all inbound sms automations  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | Page number | | limit | query | integer(int32) | false | Number of records per page |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SmsApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View SMS Inbound Automations
  result = api_instance.view_sms_inbound_automations(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_sms_inbound_automations: #{e}"
end
```

#### Using the view_sms_inbound_automations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewSmsInboundAutomations>, Integer, Hash)> view_sms_inbound_automations_with_http_info(opts)

```ruby
begin
  # View SMS Inbound Automations
  data, status_code, headers = api_instance.view_sms_inbound_automations_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewSmsInboundAutomations>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_sms_inbound_automations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewSmsInboundAutomations**](ViewSmsInboundAutomations.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_sms_receipts

> <ViewSmsReceipts> view_sms_receipts(opts)

View SMS Receipts

Use this endpoint to retrieve <a href=\"https://help.clicksend.com/article/49eq1qdcui-how-do-i-receive-sms-delivery-receipts-delivery-status-updates\" target=\"_blank\">SMS delivery receipts</a> sent by your recipient.  To be able to view receipts, add a <a href=\"https://help.clicksend.com/en/articles/42317-delivery-notifications-reports\" target=\"_blank\">delivery report</a> rule with the Action set to **POLL** in the Dashboard, or use the [**Create SMS Delivery Receipt Rule**](/automations/sms/other/create-sms-delivery-receipt-rule) endpoint.  Control [pagination](/#pagination) with the _page_ and _limit_ query parameters to specify the page of results and the number of items returned.

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

api_instance = ClickSend::SmsApi.new
opts = {
  content_type: 'application/json', # String | 
  page: 1, # Integer | The page number to retrieve. Use this parameter to navigate through the [pagination](/#pagination) results. The default value is 1.
  limit: 15 # Integer | The number of items to return per page. This parameter controls the size of each page of results. The default value is 15.
}

begin
  # View SMS Receipts
  result = api_instance.view_sms_receipts(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_sms_receipts: #{e}"
end
```

#### Using the view_sms_receipts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewSmsReceipts>, Integer, Hash)> view_sms_receipts_with_http_info(opts)

```ruby
begin
  # View SMS Receipts
  data, status_code, headers = api_instance.view_sms_receipts_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewSmsReceipts>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_sms_receipts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **page** | **Integer** | The page number to retrieve. Use this parameter to navigate through the [pagination](/#pagination) results. The default value is 1. | [optional][default to 1] |
| **limit** | **Integer** | The number of items to return per page. This parameter controls the size of each page of results. The default value is 15. | [optional][default to 15] |

### Return type

[**ViewSmsReceipts**](ViewSmsReceipts.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_sms_templates

> <ViewSmsTemplates> view_sms_templates(opts)

View SMS Templates

Use this endpoint to retrieve <a href=\"https://help.clicksend.com/article/9z9uloaz8y-sms-templates-for-different-industries\" target=\"_blank\">SMS templates</a>. You can filter the SMS templates result using the query parameters.

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

api_instance = ClickSend::SmsApi.new
opts = {
  content_type: 'application/json', # String | 
  page: 1, # Integer | The page number to retrieve. Use this parameter to navigate through the [pagination](/#pagination) results. The default value is 1.
  limit: 15, # Integer | The number of items to return per page. This parameter controls the size of each page of results. The default value is 15.
  q: 'q_example', # String | Allows filtering of results based on your search criteria. The query should be in the format `field_name:value`.  1. **Field Name**: The field within the SMS history you want to filter by. You can use the following fields:    - _template_id_ : The ID of the template   - _template_name_ : The name of the template   - _body_ : The body content of the template.          2. **Value**: The text or keyword you're searching for within the specified field. If left empty after the colon, the filter will look for all templates with any value in the **Field Name**.      For example, if you are searching for the template with the name of _sample_name_, the final query would look like this:     `q=template_name:sample_name`  <div class=\"info-box\">   <h4><i class=\"fas fa-info-circle\"></i> Note:</h4>   <div>    <p>Some characters have to be encoded. For example, if you are searching for SMS sent from the phone number +61437085284, your search query q would be:<br/></p>     <ul>       <li>q=from:%2B61437085284</li>     </ul>     <p>You can use the <a href=\"https://www.urlencoder.org/\" target=\"_blank\">URL encoder</a> to encode the text. If a character is not an alphanumeric character (A-Z, a-z, 0-9), it is typically either reserved or unsafe and should be encoded.</p>   </div> </div>
  order_by: 'order_by_example' # String | Specifies the field and order to sort the results by.  The value is composed of the field name followed by a colon and the sort direction (_asc_ for ascending or _desc_ for descending).  The default sort order is by _template_id_ in ascending order. You can use the following fields:      - _template_id_ : The ID of the Template - _template_name_ : The name of the Template - _body_ : The body content of the Template  For example, if you want to order by the _template_id_ in descending order, the query would look like this:    `order_by=template_id:desc`
}

begin
  # View SMS Templates
  result = api_instance.view_sms_templates(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_sms_templates: #{e}"
end
```

#### Using the view_sms_templates_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewSmsTemplates>, Integer, Hash)> view_sms_templates_with_http_info(opts)

```ruby
begin
  # View SMS Templates
  data, status_code, headers = api_instance.view_sms_templates_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewSmsTemplates>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_sms_templates_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **page** | **Integer** | The page number to retrieve. Use this parameter to navigate through the [pagination](/#pagination) results. The default value is 1. | [optional][default to 1] |
| **limit** | **Integer** | The number of items to return per page. This parameter controls the size of each page of results. The default value is 15. | [optional][default to 15] |
| **q** | **String** | Allows filtering of results based on your search criteria. The query should be in the format &#x60;field_name:value&#x60;.  1. **Field Name**: The field within the SMS history you want to filter by. You can use the following fields:    - _template_id_ : The ID of the template   - _template_name_ : The name of the template   - _body_ : The body content of the template.          2. **Value**: The text or keyword you&#39;re searching for within the specified field. If left empty after the colon, the filter will look for all templates with any value in the **Field Name**.      For example, if you are searching for the template with the name of _sample_name_, the final query would look like this:     &#x60;q&#x3D;template_name:sample_name&#x60;  &lt;div class&#x3D;\&quot;info-box\&quot;&gt;   &lt;h4&gt;&lt;i class&#x3D;\&quot;fas fa-info-circle\&quot;&gt;&lt;/i&gt; Note:&lt;/h4&gt;   &lt;div&gt;    &lt;p&gt;Some characters have to be encoded. For example, if you are searching for SMS sent from the phone number +61437085284, your search query q would be:&lt;br/&gt;&lt;/p&gt;     &lt;ul&gt;       &lt;li&gt;q&#x3D;from:%2B61437085284&lt;/li&gt;     &lt;/ul&gt;     &lt;p&gt;You can use the &lt;a href&#x3D;\&quot;https://www.urlencoder.org/\&quot; target&#x3D;\&quot;_blank\&quot;&gt;URL encoder&lt;/a&gt; to encode the text. If a character is not an alphanumeric character (A-Z, a-z, 0-9), it is typically either reserved or unsafe and should be encoded.&lt;/p&gt;   &lt;/div&gt; &lt;/div&gt; | [optional][default to &#39;field_name&#39;] |
| **order_by** | **String** | Specifies the field and order to sort the results by.  The value is composed of the field name followed by a colon and the sort direction (_asc_ for ascending or _desc_ for descending).  The default sort order is by _template_id_ in ascending order. You can use the following fields:      - _template_id_ : The ID of the Template - _template_name_ : The name of the Template - _body_ : The body content of the Template  For example, if you want to order by the _template_id_ in descending order, the query would look like this:    &#x60;order_by&#x3D;template_id:desc&#x60; | [optional][default to &#39;template_id:asc&#39;] |

### Return type

[**ViewSmsTemplates**](ViewSmsTemplates.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_specific_sms_receipt

> <ViewSpecificSmsReceipt> view_specific_sms_receipt(message_id, opts)

View Specific SMS Receipt

Use this endpoint to retrieve a specific <a href=\"https://help.clicksend.com/article/49eq1qdcui-how-do-i-receive-sms-delivery-receipts-delivery-status-updates\" target=\"_blank\">SMS delivery receipt</a>, including those that have been marked as read. When you send an SMS, a delivery receipt is generated and can be received.  This endpoint enables you to retrieve those receipts.

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

api_instance = ClickSend::SmsApi.new
message_id = 'message_id_example' # String | The _message_id_ of the SMS delivery receipt to retrieve
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Specific SMS Receipt
  result = api_instance.view_specific_sms_receipt(message_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_specific_sms_receipt: #{e}"
end
```

#### Using the view_specific_sms_receipt_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewSpecificSmsReceipt>, Integer, Hash)> view_specific_sms_receipt_with_http_info(message_id, opts)

```ruby
begin
  # View Specific SMS Receipt
  data, status_code, headers = api_instance.view_specific_sms_receipt_with_http_info(message_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewSpecificSmsReceipt>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsApi->view_specific_sms_receipt_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **message_id** | **String** | The _message_id_ of the SMS delivery receipt to retrieve |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewSpecificSmsReceipt**](ViewSpecificSmsReceipt.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

