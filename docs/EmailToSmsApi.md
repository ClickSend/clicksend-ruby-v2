# ClickSend::EmailToSmsApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**add_allowed_email**](EmailToSmsApi.md#add_allowed_email) | **POST** /v3/sms/email-sms | Add Allowed Email |
| [**create_stripped_string_rule**](EmailToSmsApi.md#create_stripped_string_rule) | **POST** /v3/sms/email-sms-stripped-strings | Create Stripped String Rule |
| [**delete_stripped_string_rule**](EmailToSmsApi.md#delete_stripped_string_rule) | **DELETE** /v3/sms/email-sms-stripped-strings/{rule_id} | Delete Stripped String Rule |
| [**update_stripped_string_rule**](EmailToSmsApi.md#update_stripped_string_rule) | **PUT** /v3/sms/email-sms-stripped-strings/{rule_id} | Update Stripped String Rule |
| [**view_allowed_emails**](EmailToSmsApi.md#view_allowed_emails) | **GET** /v3/sms/email-sms | View Allowed Emails |
| [**view_stripped_string_rule**](EmailToSmsApi.md#view_stripped_string_rule) | **GET** /v3/sms/email-sms-stripped-strings/{rule_id} | View Stripped String Rule |
| [**view_stripped_string_rules**](EmailToSmsApi.md#view_stripped_string_rules) | **GET** /v3/sms/email-sms-stripped-strings | View Stripped String Rules |


## add_allowed_email

> <AddAllowedEmail> add_allowed_email(opts)

Add Allowed Email

_Create email to sms allowed address_  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | email_address | string | true | none | Your email address | | from | string | false | [yes](http://help.clicksend.com/SMS/what-is-a-sender-id-or-sender-number) | Your sender id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailToSmsApi.new
opts = {
  content_type: 'application/json', # String | 
  add_allowed_email_request: ClickSend::AddAllowedEmailRequest.new # AddAllowedEmailRequest | 
}

begin
  # Add Allowed Email
  result = api_instance.add_allowed_email(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailToSmsApi->add_allowed_email: #{e}"
end
```

#### Using the add_allowed_email_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AddAllowedEmail>, Integer, Hash)> add_allowed_email_with_http_info(opts)

```ruby
begin
  # Add Allowed Email
  data, status_code, headers = api_instance.add_allowed_email_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AddAllowedEmail>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailToSmsApi->add_allowed_email_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **add_allowed_email_request** | [**AddAllowedEmailRequest**](AddAllowedEmailRequest.md) |  | [optional] |

### Return type

[**AddAllowedEmail**](AddAllowedEmail.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_stripped_string_rule

> <CreateStrippedStringRule> create_stripped_string_rule(opts)

Create Stripped String Rule

_Create email to sms stripped string rule_  Create email to sms stripped string rules  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | stripped-string | body | string | true | String to be stripped. |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailToSmsApi.new
opts = {
  content_type: 'application/json', # String | 
  create_stripped_string_rule_request: ClickSend::CreateStrippedStringRuleRequest.new # CreateStrippedStringRuleRequest | 
}

begin
  # Create Stripped String Rule
  result = api_instance.create_stripped_string_rule(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailToSmsApi->create_stripped_string_rule: #{e}"
end
```

#### Using the create_stripped_string_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateStrippedStringRule>, Integer, Hash)> create_stripped_string_rule_with_http_info(opts)

```ruby
begin
  # Create Stripped String Rule
  data, status_code, headers = api_instance.create_stripped_string_rule_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateStrippedStringRule>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailToSmsApi->create_stripped_string_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **create_stripped_string_rule_request** | [**CreateStrippedStringRuleRequest**](CreateStrippedStringRuleRequest.md) |  | [optional] |

### Return type

[**CreateStrippedStringRule**](CreateStrippedStringRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_stripped_string_rule

> <DeleteStrippedStringRule> delete_stripped_string_rule(rule_id, opts)

Delete Stripped String Rule

_Delete email to sms stripped string rule_  Delete email to sms stripped string rule  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | rule_id | path | integer(int32) | true | Your rule id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailToSmsApi.new
rule_id = 'rule_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Delete Stripped String Rule
  result = api_instance.delete_stripped_string_rule(rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailToSmsApi->delete_stripped_string_rule: #{e}"
end
```

#### Using the delete_stripped_string_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteStrippedStringRule>, Integer, Hash)> delete_stripped_string_rule_with_http_info(rule_id, opts)

```ruby
begin
  # Delete Stripped String Rule
  data, status_code, headers = api_instance.delete_stripped_string_rule_with_http_info(rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteStrippedStringRule>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailToSmsApi->delete_stripped_string_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**DeleteStrippedStringRule**](DeleteStrippedStringRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_stripped_string_rule

> <UpdateStrippedStringRule> update_stripped_string_rule(rule_id, opts)

Update Stripped String Rule

_Update email to sms stripped string rule_  Update email to sms stripped string rule  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | rule_id | path | integer(int32) | true | Your rule id | | stripped-string | body | string | true | String to be stripped. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailToSmsApi.new
rule_id = 'rule_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  create_stripped_string_rule_request: ClickSend::CreateStrippedStringRuleRequest.new # CreateStrippedStringRuleRequest | 
}

begin
  # Update Stripped String Rule
  result = api_instance.update_stripped_string_rule(rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailToSmsApi->update_stripped_string_rule: #{e}"
end
```

#### Using the update_stripped_string_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateStrippedStringRule>, Integer, Hash)> update_stripped_string_rule_with_http_info(rule_id, opts)

```ruby
begin
  # Update Stripped String Rule
  data, status_code, headers = api_instance.update_stripped_string_rule_with_http_info(rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateStrippedStringRule>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailToSmsApi->update_stripped_string_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **create_stripped_string_rule_request** | [**CreateStrippedStringRuleRequest**](CreateStrippedStringRuleRequest.md) |  | [optional] |

### Return type

[**UpdateStrippedStringRule**](UpdateStrippedStringRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## view_allowed_emails

> <ViewAllowedEmails> view_allowed_emails(opts)

View Allowed Emails

_Get list of email to sms allowed addresses_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailToSmsApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Allowed Emails
  result = api_instance.view_allowed_emails(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailToSmsApi->view_allowed_emails: #{e}"
end
```

#### Using the view_allowed_emails_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewAllowedEmails>, Integer, Hash)> view_allowed_emails_with_http_info(opts)

```ruby
begin
  # View Allowed Emails
  data, status_code, headers = api_instance.view_allowed_emails_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewAllowedEmails>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailToSmsApi->view_allowed_emails_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewAllowedEmails**](ViewAllowedEmails.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_stripped_string_rule

> <ViewStrippedStringRule> view_stripped_string_rule(rule_id, opts)

View Stripped String Rule

_Get email to sms stripped string rule_  Get email to sms stripped string rule  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | rule_id | path | integer(int32) | true | Your rule id |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailToSmsApi.new
rule_id = 'rule_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Stripped String Rule
  result = api_instance.view_stripped_string_rule(rule_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailToSmsApi->view_stripped_string_rule: #{e}"
end
```

#### Using the view_stripped_string_rule_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewStrippedStringRule>, Integer, Hash)> view_stripped_string_rule_with_http_info(rule_id, opts)

```ruby
begin
  # View Stripped String Rule
  data, status_code, headers = api_instance.view_stripped_string_rule_with_http_info(rule_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewStrippedStringRule>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailToSmsApi->view_stripped_string_rule_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **rule_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewStrippedStringRule**](ViewStrippedStringRule.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_stripped_string_rules

> <ViewStrippedStringRules> view_stripped_string_rules(opts)

View Stripped String Rules

_Get list of email to sms stripped string rules_  Get list of email to sms stripped string rules  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | Page number | | limit | query | integer(int32) | false | Number of records per page |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::EmailToSmsApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Stripped String Rules
  result = api_instance.view_stripped_string_rules(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling EmailToSmsApi->view_stripped_string_rules: #{e}"
end
```

#### Using the view_stripped_string_rules_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewStrippedStringRules>, Integer, Hash)> view_stripped_string_rules_with_http_info(opts)

```ruby
begin
  # View Stripped String Rules
  data, status_code, headers = api_instance.view_stripped_string_rules_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewStrippedStringRules>
rescue ClickSend::ApiError => e
  puts "Error when calling EmailToSmsApi->view_stripped_string_rules_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewStrippedStringRules**](ViewStrippedStringRules.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

