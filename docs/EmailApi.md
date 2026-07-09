# ClickSend::EmailApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**calculate_email_campaign_price**](EmailApi.md#calculate_email_campaign_price) | **POST** /v3/email-campaigns/price | Calculate Email Campaign Price |
| [**calculate_email_price**](EmailApi.md#calculate_email_price) | **POST** /v3/email/price | Calculate Email Price |
| [**cancel_email_campaign**](EmailApi.md#cancel_email_campaign) | **PUT** /v3/email-campaigns/{email_campaign_id}/cancel | Cancel Email Campaign |
| [**create_allowed_email_address**](EmailApi.md#create_allowed_email_address) | **POST** /v3/email/addresses | Create Allowed Email Address |
| [**create_email_delivery_receipt_rule**](EmailApi.md#create_email_delivery_receipt_rule) | **POST** /v3/automations/email/receipts | Create Email Delivery Receipt Rule |
| [**create_email_template**](EmailApi.md#create_email_template) | **POST** /v3/email/templates | Create Email Template |
| [**delete_allowed_email_address**](EmailApi.md#delete_allowed_email_address) | **DELETE** /v3/email/addresses/{email_address_id} | Delete Allowed Email Address |
| [**delete_email_delivery_receipt_rule**](EmailApi.md#delete_email_delivery_receipt_rule) | **DELETE** /v3/automations/email/receipts/{receipt_rule_id} | Delete Email Delivery Receipt Rule |
| [**delete_email_template**](EmailApi.md#delete_email_template) | **DELETE** /v3/email/templates/{template_id} | Delete Email Template |
| [**export_email_campaign_history**](EmailApi.md#export_email_campaign_history) | **GET** /v3/email-campaigns/{email_campaign_id}/history/export | Export Email Campaign History |
| [**export_email_history**](EmailApi.md#export_email_history) | **GET** /v3/email/history/export | Export Email History |
| [**send_email**](EmailApi.md#send_email) | **POST** /v3/email/send | Send Email |
| [**send_email_campaign**](EmailApi.md#send_email_campaign) | **POST** /v3/email-campaigns/send | Send Email Campaign |
| [**send_email_verification_token**](EmailApi.md#send_email_verification_token) | **PUT** /v3/email/address-verify/{email_address_id}/send | Send Email Verification Token |
| [**update_email_campaign**](EmailApi.md#update_email_campaign) | **PUT** /v3/email-campaigns/{email_campaign_id} | Update Email Campaign |
| [**update_email_delivery_receipt_rule**](EmailApi.md#update_email_delivery_receipt_rule) | **PUT** /v3/automations/email/receipts/{receipt_rule_id} | Update Email Delivery Receipt Rule |
| [**update_email_template**](EmailApi.md#update_email_template) | **PUT** /v3/email/templates/{template_id} | Update Email Template |
| [**verify_allowed_email_address**](EmailApi.md#verify_allowed_email_address) | **PUT** /v3/email/address-verify/{email_address_id}/verify/{activation_token} | Verify Allowed Email Address |
| [**view_all_email_campaigns**](EmailApi.md#view_all_email_campaigns) | **GET** /v3/email-campaigns | View All Email Campaigns |
| [**view_allowed_email_address**](EmailApi.md#view_allowed_email_address) | **GET** /v3/email/addresses/{email_address_id} | View Allowed Email Address |
| [**view_allowed_email_addresses**](EmailApi.md#view_allowed_email_addresses) | **GET** /v3/email/addresses | View Allowed Email Addresses |
| [**view_email_campaign**](EmailApi.md#view_email_campaign) | **GET** /v3/email-campaigns/{email_campaign_id} | View Email Campaign |
| [**view_email_campaign_history**](EmailApi.md#view_email_campaign_history) | **GET** /v3/email-campaigns/{email_campaign_id}/history | View Email Campaign History |
| [**view_email_delivery_receipt_rule**](EmailApi.md#view_email_delivery_receipt_rule) | **GET** /v3/automations/email/receipts/{receipt_rule_id} | View Email Delivery Receipt Rule |
| [**view_email_delivery_receipt_rules**](EmailApi.md#view_email_delivery_receipt_rules) | **GET** /v3/automations/email/receipts | View Email Delivery Receipt Rules |
| [**view_email_history**](EmailApi.md#view_email_history) | **GET** /v3/email/history | View Email History |
| [**view_email_template**](EmailApi.md#view_email_template) | **GET** /v3/email/templates/{template_id} | View Email Template |
| [**view_email_templates**](EmailApi.md#view_email_templates) | **GET** /v3/email/templates | View Email Templates |
| [**view_master_email_template**](EmailApi.md#view_master_email_template) | **GET** /v3/email/master-templates/{template_id} | View Master Email Template |
| [**view_master_email_templates**](EmailApi.md#view_master_email_templates) | **GET** /v3/email/master-templates | View Master Email Templates |
| [**view_template_categories**](EmailApi.md#view_template_categories) | **GET** /v3/email/master-templates-categories | View Template Categories |
| [**view_template_category**](EmailApi.md#view_template_category) | **GET** /v3/email/master-templates-categories/{category_id} | View Template Category |
| [**view_templates_in_category**](EmailApi.md#view_templates_in_category) | **GET** /v3/email/master-templates-categories/{category_id}/master-templates | View Templates in Category |


## calculate_email_campaign_price

> <CalculateEmailCampaignPrice> calculate_email_campaign_price(opts)

Calculate Email Campaign Price

_Calculate email campaign price_  Calculate email campaign price  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | name | string | true | none | Your campaign name. | | subject | string | true | none | Your campaign subject. | | body | string | true | none | Your campaign message. | | from_email_address_id | number | true | none | The allowed email address id. | | from_name | string | true | none | Your name or business name. | | template_id | number | false | none | Your template id. | | list_id | number | true | none | Your contact list id. | | schedule | integer(int32) | false | none | Your schedule timestamp. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
opts = {
  content_type: 'application/json', # String | 
  calculate_email_campaign_price_request: ClickSend::CalculateEmailCampaignPriceRequest.new # CalculateEmailCampaignPriceRequest | 
}

begin
  # Calculate Email Campaign Price
  result = api_instance.calculate_email_campaign_price(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->calculate_email_campaign_price: #{e}"
end
```

#### Using the calculate_email_campaign_price_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalculateEmailCampaignPrice>, Integer, Hash)> calculate_email_campaign_price_with_http_info(opts)

```ruby
begin
  # Calculate Email Campaign Price
  data, status_code, headers = api_instance.calculate_email_campaign_price_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalculateEmailCampaignPrice>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->calculate_email_campaign_price_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **calculate_email_campaign_price_request** | [**CalculateEmailCampaignPriceRequest**](CalculateEmailCampaignPriceRequest.md) |  | [optional] |

### Return type

[**CalculateEmailCampaignPrice**](CalculateEmailCampaignPrice.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## calculate_email_price

> <CalculateEmailPrice> calculate_email_price(opts)

Calculate Email Price

_Get transactional email price_  Get transactional email price  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | to | array | true | none | Array of To Recipient items. (array of names and emails) | | cc | array | false | none | Array of Cc Recipient items. (array of names and emails) | | bcc | array | false | none | Array of Bcc Recipient items. (array of names and emails) | | from | object | true | none | From Email object. (object containing name and email) | | body | string | true | none | Body of the email. | | attachments | array | false | none | Array of Attachment items. | | schedule | number | false | none | Schedule. | | name | string | false | none | Name of person email belongs to | | email | string | true | none | Email to be used. | | content | string | true | none | The base64-encoded contents of the file. | | type | string | true | none | The type of file being attached. | | filename | string | true | none | The name of the file being attached. | | disposition | string | true | none | Inline for content that can be displayed within the email, or attachment for any other files. | | content_id | string | true | none | An ID for the content. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
opts = {
  content_type: 'application/json', # String | 
  calculate_email_price_request: ClickSend::CalculateEmailPriceRequest.new # CalculateEmailPriceRequest | 
}

begin
  # Calculate Email Price
  result = api_instance.calculate_email_price(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->calculate_email_price: #{e}"
end
```

#### Using the calculate_email_price_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalculateEmailPrice>, Integer, Hash)> calculate_email_price_with_http_info(opts)

```ruby
begin
  # Calculate Email Price
  data, status_code, headers = api_instance.calculate_email_price_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalculateEmailPrice>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->calculate_email_price_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **calculate_email_price_request** | [**CalculateEmailPriceRequest**](CalculateEmailPriceRequest.md) |  | [optional] |

### Return type

[**CalculateEmailPrice**](CalculateEmailPrice.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## cancel_email_campaign

> <CancelEmailCampaign> cancel_email_campaign(email_campaign_id, opts)

Cancel Email Campaign

_Cancel email campaign_  Cancel email campaign  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | email_campaign_id | path | integer(int32) | true | Allowed email campaign id | | date_from | query | integer(int32) | false | Start date (Unix Timestamp e.g. 1436849372) | | date_to | query | integer(int32) | false | End date (Unix Timestamp e.g. 1436879372) | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
email_campaign_id = 'email_campaign_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  cancel_email_campaign_request: ClickSend::CancelEmailCampaignRequest.new # CancelEmailCampaignRequest | 
}

begin
  # Cancel Email Campaign
  result = api_instance.cancel_email_campaign(email_campaign_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->cancel_email_campaign: #{e}"
end
```

#### Using the cancel_email_campaign_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CancelEmailCampaign>, Integer, Hash)> cancel_email_campaign_with_http_info(email_campaign_id, opts)

```ruby
begin
  # Cancel Email Campaign
  data, status_code, headers = api_instance.cancel_email_campaign_with_http_info(email_campaign_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CancelEmailCampaign>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->cancel_email_campaign_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email_campaign_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **cancel_email_campaign_request** | [**CancelEmailCampaignRequest**](CancelEmailCampaignRequest.md) |  | [optional] |

### Return type

[**CancelEmailCampaign**](CancelEmailCampaign.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_allowed_email_address

> <CreateAllowedEmailAddress> create_allowed_email_address(opts)

Create Allowed Email Address

_Create allowed Email Address_  Create allowed Email Address  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | body | body | string | true | Email to be allowed. |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
opts = {
  content_type: 'application/json', # String | 
  create_allowed_email_address_request: ClickSend::CreateAllowedEmailAddressRequest.new # CreateAllowedEmailAddressRequest | 
}

begin
  # Create Allowed Email Address
  result = api_instance.create_allowed_email_address(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->create_allowed_email_address: #{e}"
end
```

#### Using the create_allowed_email_address_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateAllowedEmailAddress>, Integer, Hash)> create_allowed_email_address_with_http_info(opts)

```ruby
begin
  # Create Allowed Email Address
  data, status_code, headers = api_instance.create_allowed_email_address_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateAllowedEmailAddress>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->create_allowed_email_address_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **create_allowed_email_address_request** | [**CreateAllowedEmailAddressRequest**](CreateAllowedEmailAddressRequest.md) |  | [optional] |

### Return type

[**CreateAllowedEmailAddress**](CreateAllowedEmailAddress.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_email_delivery_receipt_rule

> <CreateEmailDeliveryReceiptRule> create_email_delivery_receipt_rule(opts)

Create Email Delivery Receipt Rule

_Create email delivery receipt automations_  Create email delivery receipt automations  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | rule_name | string | true | none | Rule Name. | | match_type | number | true | none | Match Type. 0=All reports. | | action | string | true | none | Action to be taken (AUTO_REPLY, EMAIL_USER, EMAIL_FIXED, URL, SMS, POLL, GROUP_SMS, MOVE_CONTACT, CREATE_CONTACT, CREATE_CONTACT_PLUS_EMAIL, CREATE_CONTACT_PLUS_NAME_EMAIL CREATE_CONTACT_PLUS_NAME, SMPP, NONE). | | action_address | string | true | none | Action address. | | enabled | number | true | none | Enabled: Disabled=0 or Enabled=1. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
opts = {
  content_type: 'application/json', # String | 
  create_sms_delivery_receipt_rule_request: ClickSend::CreateSmsDeliveryReceiptRuleRequest.new # CreateSmsDeliveryReceiptRuleRequest | 
}

begin
  # Create Email Delivery Receipt Rule
  result = api_instance.create_email_delivery_receipt_rule(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->create_email_delivery_receipt_rule: #{e}"
end
```

#### Using the create_email_delivery_receipt_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateEmailDeliveryReceiptRule>, Integer, Hash)> create_email_delivery_receipt_rule_with_http_info(opts)

```ruby
begin
  # Create Email Delivery Receipt Rule
  data, status_code, headers = api_instance.create_email_delivery_receipt_rule_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateEmailDeliveryReceiptRule>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->create_email_delivery_receipt_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **create_sms_delivery_receipt_rule_request** | [**CreateSmsDeliveryReceiptRuleRequest**](CreateSmsDeliveryReceiptRuleRequest.md) |  | [optional] |

### Return type

[**CreateEmailDeliveryReceiptRule**](CreateEmailDeliveryReceiptRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_email_template

> <CreateEmailTemplate> create_email_template(opts)

Create Email Template

_Create email template_  Create email template  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | template_name | string | true | none | The intended name for the new template. | | template_id_master | number | true | none | The ID of the master template you want to base on. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
opts = {
  content_type: 'application/json', # String | 
  create_email_template_request: ClickSend::CreateEmailTemplateRequest.new # CreateEmailTemplateRequest | 
}

begin
  # Create Email Template
  result = api_instance.create_email_template(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->create_email_template: #{e}"
end
```

#### Using the create_email_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateEmailTemplate>, Integer, Hash)> create_email_template_with_http_info(opts)

```ruby
begin
  # Create Email Template
  data, status_code, headers = api_instance.create_email_template_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateEmailTemplate>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->create_email_template_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **create_email_template_request** | [**CreateEmailTemplateRequest**](CreateEmailTemplateRequest.md) |  | [optional] |

### Return type

[**CreateEmailTemplate**](CreateEmailTemplate.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_allowed_email_address

> <DeleteAllowedEmailAddress> delete_allowed_email_address(email_address_id, opts)

Delete Allowed Email Address

_Delete specific email address_  Delete specific email address  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | email_address_id | path | integer(int32) | true | Allowed email address id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
email_address_id = 'email_address_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Delete Allowed Email Address
  result = api_instance.delete_allowed_email_address(email_address_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->delete_allowed_email_address: #{e}"
end
```

#### Using the delete_allowed_email_address_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteAllowedEmailAddress>, Integer, Hash)> delete_allowed_email_address_with_http_info(email_address_id, opts)

```ruby
begin
  # Delete Allowed Email Address
  data, status_code, headers = api_instance.delete_allowed_email_address_with_http_info(email_address_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteAllowedEmailAddress>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->delete_allowed_email_address_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email_address_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**DeleteAllowedEmailAddress**](DeleteAllowedEmailAddress.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_email_delivery_receipt_rule

> <DeleteEmailDeliveryReceiptRule> delete_email_delivery_receipt_rule(receipt_rule_id, opts)

Delete Email Delivery Receipt Rule

_Delete email delivery receipt automation_  Delete email delivery receipt automation  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | receipt_rule_id | path | integer(int32) | true | Receipt rule id |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  This endpoint requires authentication, [more info...](/#authentication)   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
receipt_rule_id = 'receipt_rule_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Delete Email Delivery Receipt Rule
  result = api_instance.delete_email_delivery_receipt_rule(receipt_rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->delete_email_delivery_receipt_rule: #{e}"
end
```

#### Using the delete_email_delivery_receipt_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteEmailDeliveryReceiptRule>, Integer, Hash)> delete_email_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)

```ruby
begin
  # Delete Email Delivery Receipt Rule
  data, status_code, headers = api_instance.delete_email_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteEmailDeliveryReceiptRule>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->delete_email_delivery_receipt_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **receipt_rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**DeleteEmailDeliveryReceiptRule**](DeleteEmailDeliveryReceiptRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_email_template

> <DeleteEmailTemplate> delete_email_template(template_id, opts)

Delete Email Template

_Delete user email template_  Delete user email template  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | template_id | path | integer(int32) | true | Email template id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
template_id = 'template_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Delete Email Template
  result = api_instance.delete_email_template(template_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->delete_email_template: #{e}"
end
```

#### Using the delete_email_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteEmailTemplate>, Integer, Hash)> delete_email_template_with_http_info(template_id, opts)

```ruby
begin
  # Delete Email Template
  data, status_code, headers = api_instance.delete_email_template_with_http_info(template_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteEmailTemplate>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->delete_email_template_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **template_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**DeleteEmailTemplate**](DeleteEmailTemplate.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## export_email_campaign_history

> export_email_campaign_history(email_campaign_id, opts)

Export Email Campaign History

_Export specific email campaign history_  Export specific email campaign history  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | email_campaign_id | path | integer(int32) | true | Allowed email campaign id | | date_from | query | integer(int32) | false | Start date (Unix Timestamp e.g. 1436849372) | | date_to | query | integer(int32) | false | End date (Unix Timestamp e.g. 1436879372) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
email_campaign_id = 'email_campaign_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Export Email Campaign History
  api_instance.export_email_campaign_history(email_campaign_id, opts)
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->export_email_campaign_history: #{e}"
end
```

#### Using the export_email_campaign_history_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> export_email_campaign_history_with_http_info(email_campaign_id, opts)

```ruby
begin
  # Export Email Campaign History
  data, status_code, headers = api_instance.export_email_campaign_history_with_http_info(email_campaign_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->export_email_campaign_history_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email_campaign_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

nil (empty response body)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## export_email_history

> <ExportEmailHistory> export_email_history(opts)

Export Email History

_Export all Transactional Email history_  Export all Transactional Email history  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | filename | query | string | true | Filename to download history as | | date_from | query | integer(int32) | false | Start date (Unix Timestamp e.g. 1436849372) | | date_to | query | integer(int32) | false | End date (Unix Timestamp e.g. 1436879372) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Export Email History
  result = api_instance.export_email_history(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->export_email_history: #{e}"
end
```

#### Using the export_email_history_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ExportEmailHistory>, Integer, Hash)> export_email_history_with_http_info(opts)

```ruby
begin
  # Export Email History
  data, status_code, headers = api_instance.export_email_history_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ExportEmailHistory>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->export_email_history_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ExportEmailHistory**](ExportEmailHistory.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## send_email

> <SendEmail> send_email(opts)

Send Email

_Send transactional email_  Send transactional email  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | to | array | true | none | Array of To Recipient items. (array of names and emails) | | cc | array | false | none | Array of Cc Recipient items. (array of names and emails) | | bcc | array | false | none | Array of Bcc Recipient items. (array of names and emails) | | from | object | true | none | From Email object. (object containing name and email) | | body | string | true | none | Body of the email. | | attachments | array | false | none | Array of Attachment items. | | schedule | number | false | none | Schedule. | | name | string | false | none | Name of person email belongs to | | email | string | true | none | Email to be used. | | content | string | true | none | The base64-encoded contents of the file. | | type | string | true | none | The type of file being attached. | | filename | string | true | none | The name of the file being attached. | | disposition | string | true | none | Inline for content that can be displayed within the email, or attachment for any other files. | | content_id | string | true | none | An ID for the content. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
opts = {
  content_type: 'application/json', # String | 
  send_email_request: ClickSend::SendEmailRequest.new # SendEmailRequest | 
}

begin
  # Send Email
  result = api_instance.send_email(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->send_email: #{e}"
end
```

#### Using the send_email_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendEmail>, Integer, Hash)> send_email_with_http_info(opts)

```ruby
begin
  # Send Email
  data, status_code, headers = api_instance.send_email_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendEmail>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->send_email_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **send_email_request** | [**SendEmailRequest**](SendEmailRequest.md) |  | [optional] |

### Return type

[**SendEmail**](SendEmail.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## send_email_campaign

> <SendEmailCampaign> send_email_campaign(opts)

Send Email Campaign

_Send email campaign_  Send email campaign  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | name | string | true | none | Your campaign name. | | subject | string | true | none | Your campaign subject. | | body | string | true | none | Your campaign message. | | from_email_address_id | number | true | none | The allowed email address id. | | from_name | string | true | none | Your name or business name. | | template_id | number | false | none | Your template id. | | list_id | number | true | none | Your contact list id. | | schedule | integer(int32) | false | none | Your schedule timestamp. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
opts = {
  content_type: 'application/json', # String | 
  send_email_campaign_request: ClickSend::SendEmailCampaignRequest.new # SendEmailCampaignRequest | 
}

begin
  # Send Email Campaign
  result = api_instance.send_email_campaign(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->send_email_campaign: #{e}"
end
```

#### Using the send_email_campaign_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendEmailCampaign>, Integer, Hash)> send_email_campaign_with_http_info(opts)

```ruby
begin
  # Send Email Campaign
  data, status_code, headers = api_instance.send_email_campaign_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendEmailCampaign>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->send_email_campaign_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **send_email_campaign_request** | [**SendEmailCampaignRequest**](SendEmailCampaignRequest.md) |  | [optional] |

### Return type

[**SendEmailCampaign**](SendEmailCampaign.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## send_email_verification_token

> <SendEmailVerificationToken> send_email_verification_token(email_address_id, opts)

Send Email Verification Token

_Send verification token_  Send verification token  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | email_address_id | path | integer(int32) | true | Allowed email address id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
email_address_id = 'email_address_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  send_email_verification_token_request: ClickSend::SendEmailVerificationTokenRequest.new # SendEmailVerificationTokenRequest | 
}

begin
  # Send Email Verification Token
  result = api_instance.send_email_verification_token(email_address_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->send_email_verification_token: #{e}"
end
```

#### Using the send_email_verification_token_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendEmailVerificationToken>, Integer, Hash)> send_email_verification_token_with_http_info(email_address_id, opts)

```ruby
begin
  # Send Email Verification Token
  data, status_code, headers = api_instance.send_email_verification_token_with_http_info(email_address_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendEmailVerificationToken>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->send_email_verification_token_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email_address_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **send_email_verification_token_request** | [**SendEmailVerificationTokenRequest**](SendEmailVerificationTokenRequest.md) |  | [optional] |

### Return type

[**SendEmailVerificationToken**](SendEmailVerificationToken.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_email_campaign

> <UpdateEmailCampaign> update_email_campaign(email_campaign_id, opts)

Update Email Campaign

_Edit email campaign_  Edit email campaign  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | email_campaign_id | path | integer(int32) | true | Allowed email campaign id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
email_campaign_id = 'email_campaign_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  update_email_campaign_request: ClickSend::UpdateEmailCampaignRequest.new # UpdateEmailCampaignRequest | 
}

begin
  # Update Email Campaign
  result = api_instance.update_email_campaign(email_campaign_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->update_email_campaign: #{e}"
end
```

#### Using the update_email_campaign_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateEmailCampaign>, Integer, Hash)> update_email_campaign_with_http_info(email_campaign_id, opts)

```ruby
begin
  # Update Email Campaign
  data, status_code, headers = api_instance.update_email_campaign_with_http_info(email_campaign_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateEmailCampaign>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->update_email_campaign_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email_campaign_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **update_email_campaign_request** | [**UpdateEmailCampaignRequest**](UpdateEmailCampaignRequest.md) |  | [optional] |

### Return type

[**UpdateEmailCampaign**](UpdateEmailCampaign.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_email_delivery_receipt_rule

> <UpdateEmailDeliveryReceiptRule> update_email_delivery_receipt_rule(receipt_rule_id, opts)

Update Email Delivery Receipt Rule

_Update email delivery receipt automation_  Update email delivery receipt automation  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | receipt_rule_id | path | integer(int32) | true | Receipt rule id |  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | rule_name | string | true | none | Rule Name. | | match_type | number | true | none | Match Type. 0=All reports. | | action | string | true | none | Action to be taken (AUTO_REPLY, EMAIL_USER, EMAIL_FIXED, URL, SMS, POLL, GROUP_SMS, MOVE_CONTACT, CREATE_CONTACT, CREATE_CONTACT_PLUS_EMAIL, CREATE_CONTACT_PLUS_NAME_EMAIL CREATE_CONTACT_PLUS_NAME, SMPP, NONE). | | action_address | string | true | none | Action address. | | enabled | number | true | none | Enabled: Disabled=0 or Enabled=1. |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
receipt_rule_id = 'receipt_rule_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  create_sms_delivery_receipt_rule_request: ClickSend::CreateSmsDeliveryReceiptRuleRequest.new # CreateSmsDeliveryReceiptRuleRequest | 
}

begin
  # Update Email Delivery Receipt Rule
  result = api_instance.update_email_delivery_receipt_rule(receipt_rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->update_email_delivery_receipt_rule: #{e}"
end
```

#### Using the update_email_delivery_receipt_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateEmailDeliveryReceiptRule>, Integer, Hash)> update_email_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)

```ruby
begin
  # Update Email Delivery Receipt Rule
  data, status_code, headers = api_instance.update_email_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateEmailDeliveryReceiptRule>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->update_email_delivery_receipt_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **receipt_rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **create_sms_delivery_receipt_rule_request** | [**CreateSmsDeliveryReceiptRuleRequest**](CreateSmsDeliveryReceiptRuleRequest.md) |  | [optional] |

### Return type

[**UpdateEmailDeliveryReceiptRule**](UpdateEmailDeliveryReceiptRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_email_template

> <UpdateEmailTemplate> update_email_template(template_id, opts)

Update Email Template

_Update email template_  Update email template  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | template_id | path | integer(int32) | true | Email template id |  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | template_name | string | false | none | The intended name for the template. | | body | string | true | none | Your template body. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
template_id = 'template_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  update_email_template_request: ClickSend::UpdateEmailTemplateRequest.new # UpdateEmailTemplateRequest | 
}

begin
  # Update Email Template
  result = api_instance.update_email_template(template_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->update_email_template: #{e}"
end
```

#### Using the update_email_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateEmailTemplate>, Integer, Hash)> update_email_template_with_http_info(template_id, opts)

```ruby
begin
  # Update Email Template
  data, status_code, headers = api_instance.update_email_template_with_http_info(template_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateEmailTemplate>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->update_email_template_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **template_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **update_email_template_request** | [**UpdateEmailTemplateRequest**](UpdateEmailTemplateRequest.md) |  | [optional] |

### Return type

[**UpdateEmailTemplate**](UpdateEmailTemplate.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## verify_allowed_email_address

> <VerifyAllowedEmailAddress> verify_allowed_email_address(email_address_id, activation_token, opts)

Verify Allowed Email Address

_Verify email address using verification token_  Verify email address using verification token  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | email_address_id | path | integer(int32) | true | Allowed email address id | | activation_token | path | string | true | Your activation token. |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
email_address_id = 'email_address_id_example' # String | 
activation_token = 'activation_token_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  verify_allowed_email_address_request: ClickSend::VerifyAllowedEmailAddressRequest.new # VerifyAllowedEmailAddressRequest | 
}

begin
  # Verify Allowed Email Address
  result = api_instance.verify_allowed_email_address(email_address_id, activation_token, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->verify_allowed_email_address: #{e}"
end
```

#### Using the verify_allowed_email_address_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<VerifyAllowedEmailAddress>, Integer, Hash)> verify_allowed_email_address_with_http_info(email_address_id, activation_token, opts)

```ruby
begin
  # Verify Allowed Email Address
  data, status_code, headers = api_instance.verify_allowed_email_address_with_http_info(email_address_id, activation_token, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <VerifyAllowedEmailAddress>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->verify_allowed_email_address_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email_address_id** | **String** |  |  |
| **activation_token** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **verify_allowed_email_address_request** | [**VerifyAllowedEmailAddressRequest**](VerifyAllowedEmailAddressRequest.md) |  | [optional] |

### Return type

[**VerifyAllowedEmailAddress**](VerifyAllowedEmailAddress.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## view_all_email_campaigns

> <ViewAllEmailCampaigns> view_all_email_campaigns(opts)

View All Email Campaigns

_Get all email campaigns_  Get all email campaigns  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | Page number | | limit | query | integer(int32) | false | Number of records per page |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View All Email Campaigns
  result = api_instance.view_all_email_campaigns(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_all_email_campaigns: #{e}"
end
```

#### Using the view_all_email_campaigns_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewAllEmailCampaigns>, Integer, Hash)> view_all_email_campaigns_with_http_info(opts)

```ruby
begin
  # View All Email Campaigns
  data, status_code, headers = api_instance.view_all_email_campaigns_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewAllEmailCampaigns>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_all_email_campaigns_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewAllEmailCampaigns**](ViewAllEmailCampaigns.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_allowed_email_address

> <ViewAllowedEmailAddress> view_allowed_email_address(email_address_id, opts)

View Allowed Email Address

_Get specific email address_  Get specific email address  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | email_address_id | path | integer(int32) | true | Allowed email address id |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
email_address_id = 'email_address_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Allowed Email Address
  result = api_instance.view_allowed_email_address(email_address_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_allowed_email_address: #{e}"
end
```

#### Using the view_allowed_email_address_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewAllowedEmailAddress>, Integer, Hash)> view_allowed_email_address_with_http_info(email_address_id, opts)

```ruby
begin
  # View Allowed Email Address
  data, status_code, headers = api_instance.view_allowed_email_address_with_http_info(email_address_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewAllowedEmailAddress>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_allowed_email_address_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email_address_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewAllowedEmailAddress**](ViewAllowedEmailAddress.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_allowed_email_addresses

> <ViewAllowedEmailAddresses> view_allowed_email_addresses(opts)

View Allowed Email Addresses

_Get all email addresses_  Get all email addresses  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | Page number | | limit | query | integer(int32) | false | Number of records per page |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Allowed Email Addresses
  result = api_instance.view_allowed_email_addresses(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_allowed_email_addresses: #{e}"
end
```

#### Using the view_allowed_email_addresses_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewAllowedEmailAddresses>, Integer, Hash)> view_allowed_email_addresses_with_http_info(opts)

```ruby
begin
  # View Allowed Email Addresses
  data, status_code, headers = api_instance.view_allowed_email_addresses_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewAllowedEmailAddresses>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_allowed_email_addresses_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewAllowedEmailAddresses**](ViewAllowedEmailAddresses.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_email_campaign

> <ViewEmailCampaign> view_email_campaign(email_campaign_id, opts)

View Email Campaign

_Get specific email campaign_  Get specific email campaign  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
email_campaign_id = 'email_campaign_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Email Campaign
  result = api_instance.view_email_campaign(email_campaign_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_email_campaign: #{e}"
end
```

#### Using the view_email_campaign_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewEmailCampaign>, Integer, Hash)> view_email_campaign_with_http_info(email_campaign_id, opts)

```ruby
begin
  # View Email Campaign
  data, status_code, headers = api_instance.view_email_campaign_with_http_info(email_campaign_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewEmailCampaign>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_email_campaign_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email_campaign_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewEmailCampaign**](ViewEmailCampaign.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_email_campaign_history

> <ViewEmailCampaignHistory> view_email_campaign_history(email_campaign_id, opts)

View Email Campaign History

_Get specific email campaign history_  Get specific email campaign history   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
email_campaign_id = 'email_campaign_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Email Campaign History
  result = api_instance.view_email_campaign_history(email_campaign_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_email_campaign_history: #{e}"
end
```

#### Using the view_email_campaign_history_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewEmailCampaignHistory>, Integer, Hash)> view_email_campaign_history_with_http_info(email_campaign_id, opts)

```ruby
begin
  # View Email Campaign History
  data, status_code, headers = api_instance.view_email_campaign_history_with_http_info(email_campaign_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewEmailCampaignHistory>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_email_campaign_history_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **email_campaign_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewEmailCampaignHistory**](ViewEmailCampaignHistory.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_email_delivery_receipt_rule

> <ViewEmailDeliveryReceiptRule> view_email_delivery_receipt_rule(receipt_rule_id, opts)

View Email Delivery Receipt Rule

_Get specific email delivery receipt automation_  Get specific email delivery receipt automation  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | receipt_rule_id | path | integer(int32) | true | Receipt rule id |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
receipt_rule_id = 'receipt_rule_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Email Delivery Receipt Rule
  result = api_instance.view_email_delivery_receipt_rule(receipt_rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_email_delivery_receipt_rule: #{e}"
end
```

#### Using the view_email_delivery_receipt_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewEmailDeliveryReceiptRule>, Integer, Hash)> view_email_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)

```ruby
begin
  # View Email Delivery Receipt Rule
  data, status_code, headers = api_instance.view_email_delivery_receipt_rule_with_http_info(receipt_rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewEmailDeliveryReceiptRule>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_email_delivery_receipt_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **receipt_rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewEmailDeliveryReceiptRule**](ViewEmailDeliveryReceiptRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_email_delivery_receipt_rules

> <ViewEmailDeliveryReceiptRules> view_email_delivery_receipt_rules(opts)

View Email Delivery Receipt Rules

_Get all email delivery receipt automations_  Get all email delivery receipt automations  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | Page number | | limit | query | integer(int32) | false | Number of records per page |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Email Delivery Receipt Rules
  result = api_instance.view_email_delivery_receipt_rules(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_email_delivery_receipt_rules: #{e}"
end
```

#### Using the view_email_delivery_receipt_rules_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewEmailDeliveryReceiptRules>, Integer, Hash)> view_email_delivery_receipt_rules_with_http_info(opts)

```ruby
begin
  # View Email Delivery Receipt Rules
  data, status_code, headers = api_instance.view_email_delivery_receipt_rules_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewEmailDeliveryReceiptRules>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_email_delivery_receipt_rules_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewEmailDeliveryReceiptRules**](ViewEmailDeliveryReceiptRules.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_email_history

> <ViewEmailHistory> view_email_history(opts)

View Email History

_Get all transactional email history_  Get all transactional email history  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | date_from | query | integer(int32) | false | Start date (Unix Timestamp e.g. 1436849372) | | date_to | query | integer(int32) | false | End date (Unix Timestamp e.g. 1436879372) | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Email History
  result = api_instance.view_email_history(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_email_history: #{e}"
end
```

#### Using the view_email_history_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewEmailHistory>, Integer, Hash)> view_email_history_with_http_info(opts)

```ruby
begin
  # View Email History
  data, status_code, headers = api_instance.view_email_history_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewEmailHistory>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_email_history_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewEmailHistory**](ViewEmailHistory.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_email_template

> <ViewEmailTemplate> view_email_template(template_id, opts)

View Email Template

_Get specific user email template_  Get specific user email templates  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | template_id | path | integer(int32) | true | Email template id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
template_id = 'template_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Email Template
  result = api_instance.view_email_template(template_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_email_template: #{e}"
end
```

#### Using the view_email_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewEmailTemplate>, Integer, Hash)> view_email_template_with_http_info(template_id, opts)

```ruby
begin
  # View Email Template
  data, status_code, headers = api_instance.view_email_template_with_http_info(template_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewEmailTemplate>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_email_template_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **template_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewEmailTemplate**](ViewEmailTemplate.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_email_templates

> <ViewEmailTemplates> view_email_templates(opts)

View Email Templates

_Get all user email templates_  Get all user email templates  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | Page number | | limit | query | integer(int32) | false | Number of records per page |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Email Templates
  result = api_instance.view_email_templates(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_email_templates: #{e}"
end
```

#### Using the view_email_templates_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewEmailTemplates>, Integer, Hash)> view_email_templates_with_http_info(opts)

```ruby
begin
  # View Email Templates
  data, status_code, headers = api_instance.view_email_templates_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewEmailTemplates>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_email_templates_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewEmailTemplates**](ViewEmailTemplates.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_master_email_template

> <ViewMasterEmailTemplate> view_master_email_template(template_id, opts)

View Master Email Template

_Get specific master email template_  Get specific master email template  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | template_id | path | integer(int32) | true | Email template id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
template_id = 'template_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Master Email Template
  result = api_instance.view_master_email_template(template_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_master_email_template: #{e}"
end
```

#### Using the view_master_email_template_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewMasterEmailTemplate>, Integer, Hash)> view_master_email_template_with_http_info(template_id, opts)

```ruby
begin
  # View Master Email Template
  data, status_code, headers = api_instance.view_master_email_template_with_http_info(template_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewMasterEmailTemplate>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_master_email_template_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **template_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewMasterEmailTemplate**](ViewMasterEmailTemplate.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_master_email_templates

> <ViewMasterEmailTemplates> view_master_email_templates(opts)

View Master Email Templates

_Get all master email templates._  Get all master email templates.  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | Page number | | limit | query | integer(int32) | false | Number of records per page |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Master Email Templates
  result = api_instance.view_master_email_templates(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_master_email_templates: #{e}"
end
```

#### Using the view_master_email_templates_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewMasterEmailTemplates>, Integer, Hash)> view_master_email_templates_with_http_info(opts)

```ruby
begin
  # View Master Email Templates
  data, status_code, headers = api_instance.view_master_email_templates_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewMasterEmailTemplates>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_master_email_templates_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewMasterEmailTemplates**](ViewMasterEmailTemplates.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_template_categories

> <ViewTemplateCategories> view_template_categories(opts)

View Template Categories

_Get all master email template categories_  Get all master email template categories  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | Page number | | limit | query | integer(int32) | false | Number of records per page |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Template Categories
  result = api_instance.view_template_categories(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_template_categories: #{e}"
end
```

#### Using the view_template_categories_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewTemplateCategories>, Integer, Hash)> view_template_categories_with_http_info(opts)

```ruby
begin
  # View Template Categories
  data, status_code, headers = api_instance.view_template_categories_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewTemplateCategories>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_template_categories_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewTemplateCategories**](ViewTemplateCategories.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_template_category

> <ViewTemplateCategory> view_template_category(category_id, opts)

View Template Category

_Get specific master email template category_  Get specific master email template category  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | category_id | path | integer(int32) | true | Email category id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
category_id = 'category_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Template Category
  result = api_instance.view_template_category(category_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_template_category: #{e}"
end
```

#### Using the view_template_category_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewTemplateCategory>, Integer, Hash)> view_template_category_with_http_info(category_id, opts)

```ruby
begin
  # View Template Category
  data, status_code, headers = api_instance.view_template_category_with_http_info(category_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewTemplateCategory>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_template_category_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **category_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewTemplateCategory**](ViewTemplateCategory.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_templates_in_category

> <ViewTemplatesInCategory> view_templates_in_category(category_id, opts)

View Templates in Category

_Get all master email templates in a category_  Get all master email templates in a category  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | category_id | path | integer(int32) | true | Email category id | | page | query | integer(int32) | false | Page number | | limit | query | integer(int32) | false | Number of records per page |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailApi.new
category_id = 'category_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Templates in Category
  result = api_instance.view_templates_in_category(category_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_templates_in_category: #{e}"
end
```

#### Using the view_templates_in_category_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewTemplatesInCategory>, Integer, Hash)> view_templates_in_category_with_http_info(category_id, opts)

```ruby
begin
  # View Templates in Category
  data, status_code, headers = api_instance.view_templates_in_category_with_http_info(category_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewTemplatesInCategory>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailApi->view_templates_in_category_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **category_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewTemplatesInCategory**](ViewTemplatesInCategory.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

