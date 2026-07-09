# ClickSend::ResellerApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_reseller_account**](ResellerApi.md#create_reseller_account) | **POST** /v3/reseller/accounts | Create Reseller Account |
| [**reseller_transfer_credit**](ResellerApi.md#reseller_transfer_credit) | **PUT** /v3/reseller/transfer-credit | Reseller Transfer Credit |
| [**update_client_account**](ResellerApi.md#update_client_account) | **PUT** /v3/reseller/accounts/{client_user_id} | Update Client Account |
| [**view_client_accounts**](ResellerApi.md#view_client_accounts) | **GET** /v3/reseller/accounts | View Client Accounts |
| [**view_specific_client_account**](ResellerApi.md#view_specific_client_account) | **GET** /v3/reseller/accounts/{client_user_id} | View Specific Client Account |


## create_reseller_account

> <CreateResellerAccount> create_reseller_account(opts)

Create Reseller Account

_Create reseller account_  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | username | string | true | none | Account username | | password | string | true | none | Account password (unhashed) | | user_email | string | true | none | Account email | | user_phone | string | true | none | Account phone number | | user_first_name | string | true | none | Account owner first name | | user_last_name | string | true | none | Account owner last name | | account_name | string | true | none | Account name (usually company name) | | country | string | true | none | Country of account holder |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::ResellerApi.new
opts = {
  content_type: 'application/json', # String | 
  create_reseller_account_request: ClickSend::CreateResellerAccountRequest.new # CreateResellerAccountRequest | 
}

begin
  # Create Reseller Account
  result = api_instance.create_reseller_account(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ResellerApi->create_reseller_account: #{e}"
end
```

#### Using the create_reseller_account_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateResellerAccount>, Integer, Hash)> create_reseller_account_with_http_info(opts)

```ruby
begin
  # Create Reseller Account
  data, status_code, headers = api_instance.create_reseller_account_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateResellerAccount>
rescue ClickSend::ApiError => e
  puts "Error when calling ResellerApi->create_reseller_account_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **create_reseller_account_request** | [**CreateResellerAccountRequest**](CreateResellerAccountRequest.md) |  | [optional] |

### Return type

[**CreateResellerAccount**](CreateResellerAccount.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## reseller_transfer_credit

> <ResellerTransferCredit> reseller_transfer_credit(opts)

Reseller Transfer Credit

_Transfer Credit_  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | client_user_id | integer(int32) | true | none | User ID of client | | balance | integer(int32) | true | none | Balance to transfer | | currency | string | true | none | Currency of balance to transfer |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::ResellerApi.new
opts = {
  content_type: 'application/x-www-form-urlencoded', # String | 
  update_payment_info_request: ClickSend::UpdatePaymentInfoRequest.new # UpdatePaymentInfoRequest | 
}

begin
  # Reseller Transfer Credit
  result = api_instance.reseller_transfer_credit(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ResellerApi->reseller_transfer_credit: #{e}"
end
```

#### Using the reseller_transfer_credit_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ResellerTransferCredit>, Integer, Hash)> reseller_transfer_credit_with_http_info(opts)

```ruby
begin
  # Reseller Transfer Credit
  data, status_code, headers = api_instance.reseller_transfer_credit_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ResellerTransferCredit>
rescue ClickSend::ApiError => e
  puts "Error when calling ResellerApi->reseller_transfer_credit_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **update_payment_info_request** | [**UpdatePaymentInfoRequest**](UpdatePaymentInfoRequest.md) |  | [optional] |

### Return type

[**ResellerTransferCredit**](ResellerTransferCredit.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_client_account

> <UpdateClientAccount> update_client_account(client_user_id, opts)

Update Client Account

_Update Reseller clients Account_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | client_user_id | path | integer(int32) | true | User ID of client |  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | username | string | true | none | Account username | | password | string | true | none | Account password (unhashed) | | user_email | string | true | none | Account email | | user_phone | string | true | none | Account phone number | | user_first_name | string | true | none | Account owner first name | | user_last_name | string | true | none | Account owner last name | | account_name | string | true | none | Account name (usually company name) | | country | string | true | none | Country of account holder |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::ResellerApi.new
client_user_id = 'client_user_id_example' # String | 
opts = {
  content_type: 'application/x-www-form-urlencoded', # String | 
  update_payment_info_request: ClickSend::UpdatePaymentInfoRequest.new # UpdatePaymentInfoRequest | 
}

begin
  # Update Client Account
  result = api_instance.update_client_account(client_user_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ResellerApi->update_client_account: #{e}"
end
```

#### Using the update_client_account_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateClientAccount>, Integer, Hash)> update_client_account_with_http_info(client_user_id, opts)

```ruby
begin
  # Update Client Account
  data, status_code, headers = api_instance.update_client_account_with_http_info(client_user_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateClientAccount>
rescue ClickSend::ApiError => e
  puts "Error when calling ResellerApi->update_client_account_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **client_user_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **update_payment_info_request** | [**UpdatePaymentInfoRequest**](UpdatePaymentInfoRequest.md) |  | [optional] |

### Return type

[**UpdateClientAccount**](UpdateClientAccount.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## view_client_accounts

> <ViewClientAccounts> view_client_accounts(opts)

View Client Accounts

_Get list of reseller accounts_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::ResellerApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Client Accounts
  result = api_instance.view_client_accounts(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ResellerApi->view_client_accounts: #{e}"
end
```

#### Using the view_client_accounts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewClientAccounts>, Integer, Hash)> view_client_accounts_with_http_info(opts)

```ruby
begin
  # View Client Accounts
  data, status_code, headers = api_instance.view_client_accounts_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewClientAccounts>
rescue ClickSend::ApiError => e
  puts "Error when calling ResellerApi->view_client_accounts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewClientAccounts**](ViewClientAccounts.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_specific_client_account

> <ViewSpecificClientAccount> view_specific_client_account(client_user_id, opts)

View Specific Client Account

_Get Reseller clients Account_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | client_user_id | path | integer(int32) | true | User ID of client |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::ResellerApi.new
client_user_id = 'client_user_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Specific Client Account
  result = api_instance.view_specific_client_account(client_user_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ResellerApi->view_specific_client_account: #{e}"
end
```

#### Using the view_specific_client_account_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewSpecificClientAccount>, Integer, Hash)> view_specific_client_account_with_http_info(client_user_id, opts)

```ruby
begin
  # View Specific Client Account
  data, status_code, headers = api_instance.view_specific_client_account_with_http_info(client_user_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewSpecificClientAccount>
rescue ClickSend::ApiError => e
  puts "Error when calling ResellerApi->view_specific_client_account_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **client_user_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewSpecificClientAccount**](ViewSpecificClientAccount.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

