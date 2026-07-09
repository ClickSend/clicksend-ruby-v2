# ClickSend::TransactionsApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**current_payment_info**](TransactionsApi.md#current_payment_info) | **GET** /v3/recharge/credit-card | Current Payment Info |
| [**purchase_recharge_package**](TransactionsApi.md#purchase_recharge_package) | **PUT** /v3/recharge/purchase/{package_id} | Purchase Recharge Package |
| [**update_payment_info**](TransactionsApi.md#update_payment_info) | **PUT** /v3/recharge/credit-card | Update Payment Info |
| [**view_all_transactions**](TransactionsApi.md#view_all_transactions) | **GET** /v3/recharge/transactions | View All Transactions |
| [**view_recharge_packages**](TransactionsApi.md#view_recharge_packages) | **GET** /v3/recharge/packages | View Recharge Packages |
| [**view_specific_transaction**](TransactionsApi.md#view_specific_transaction) | **GET** /v3/recharge/transactions/{transaction_id} | View Specific Transaction |


## current_payment_info

> <CurrentPaymentInfo> current_payment_info(opts)

Current Payment Info

_Get current payment info_  This endpoint returns your current payment info, we do not store credit card numbers, only a card token for security reasons.  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::TransactionsApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Current Payment Info
  result = api_instance.current_payment_info(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling TransactionsApi->current_payment_info: #{e}"
end
```

#### Using the current_payment_info_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CurrentPaymentInfo>, Integer, Hash)> current_payment_info_with_http_info(opts)

```ruby
begin
  # Current Payment Info
  data, status_code, headers = api_instance.current_payment_info_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CurrentPaymentInfo>
rescue ClickSend::ApiError => e
  puts "Error when calling TransactionsApi->current_payment_info_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**CurrentPaymentInfo**](CurrentPaymentInfo.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## purchase_recharge_package

> <PurchaseRechargePackage> purchase_recharge_package(package_id, opts)

Purchase Recharge Package

_Purchase a package_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | package_id | path | integer(int32) | true | ID of package to purchase |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::TransactionsApi.new
package_id = 'package_id_example' # String | 
opts = {
  content_type: 'application/x-www-form-urlencoded' # String | 
}

begin
  # Purchase Recharge Package
  result = api_instance.purchase_recharge_package(package_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling TransactionsApi->purchase_recharge_package: #{e}"
end
```

#### Using the purchase_recharge_package_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<PurchaseRechargePackage>, Integer, Hash)> purchase_recharge_package_with_http_info(package_id, opts)

```ruby
begin
  # Purchase Recharge Package
  data, status_code, headers = api_instance.purchase_recharge_package_with_http_info(package_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <PurchaseRechargePackage>
rescue ClickSend::ApiError => e
  puts "Error when calling TransactionsApi->purchase_recharge_package_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **package_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**PurchaseRechargePackage**](PurchaseRechargePackage.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_payment_info

> <UpdatePaymentInfo> update_payment_info(opts)

Update Payment Info

_Update credit card info_  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | number | string | true | none | Credit card number | | expiry_month | integer(int32) | true | none | Expiry month of credit card | | expiry_year | integer(int32) | true | none | Expiry year of credit card | | cvc | integer(int32) | true | none | CVC number of credit card | | name | string | true | none | Name printed on credit card | | bank_name | string | true | none | Name of bank that credit card belongs to |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::TransactionsApi.new
opts = {
  content_type: 'application/x-www-form-urlencoded', # String | 
  update_payment_info_request: ClickSend::UpdatePaymentInfoRequest.new # UpdatePaymentInfoRequest | 
}

begin
  # Update Payment Info
  result = api_instance.update_payment_info(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling TransactionsApi->update_payment_info: #{e}"
end
```

#### Using the update_payment_info_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdatePaymentInfo>, Integer, Hash)> update_payment_info_with_http_info(opts)

```ruby
begin
  # Update Payment Info
  data, status_code, headers = api_instance.update_payment_info_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdatePaymentInfo>
rescue ClickSend::ApiError => e
  puts "Error when calling TransactionsApi->update_payment_info_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **update_payment_info_request** | [**UpdatePaymentInfoRequest**](UpdatePaymentInfoRequest.md) |  | [optional] |

### Return type

[**UpdatePaymentInfo**](UpdatePaymentInfo.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## view_all_transactions

> <ViewAllTransactions> view_all_transactions(opts)

View All Transactions

_Purchase a package_  Get all transactions  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::TransactionsApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View All Transactions
  result = api_instance.view_all_transactions(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling TransactionsApi->view_all_transactions: #{e}"
end
```

#### Using the view_all_transactions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewAllTransactions>, Integer, Hash)> view_all_transactions_with_http_info(opts)

```ruby
begin
  # View All Transactions
  data, status_code, headers = api_instance.view_all_transactions_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewAllTransactions>
rescue ClickSend::ApiError => e
  puts "Error when calling TransactionsApi->view_all_transactions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewAllTransactions**](ViewAllTransactions.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_recharge_packages

> <ViewRechargePackages> view_recharge_packages(opts)

View Recharge Packages

_Get list of all packages_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | country | query | string | false | Two-letter country code ([ISO3166](https://en.wikipedia.org/wiki/ISO_3166)) |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::TransactionsApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Recharge Packages
  result = api_instance.view_recharge_packages(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling TransactionsApi->view_recharge_packages: #{e}"
end
```

#### Using the view_recharge_packages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewRechargePackages>, Integer, Hash)> view_recharge_packages_with_http_info(opts)

```ruby
begin
  # View Recharge Packages
  data, status_code, headers = api_instance.view_recharge_packages_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewRechargePackages>
rescue ClickSend::ApiError => e
  puts "Error when calling TransactionsApi->view_recharge_packages_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewRechargePackages**](ViewRechargePackages.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_specific_transaction

> <ViewSpecificTransaction> view_specific_transaction(transaction_id, opts)

View Specific Transaction

_Get specific Transaction_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | transaction_id | path | string | true | ID of transaction to retrieve |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::TransactionsApi.new
transaction_id = 'transaction_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Specific Transaction
  result = api_instance.view_specific_transaction(transaction_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling TransactionsApi->view_specific_transaction: #{e}"
end
```

#### Using the view_specific_transaction_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewSpecificTransaction>, Integer, Hash)> view_specific_transaction_with_http_info(transaction_id, opts)

```ruby
begin
  # View Specific Transaction
  data, status_code, headers = api_instance.view_specific_transaction_with_http_info(transaction_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewSpecificTransaction>
rescue ClickSend::ApiError => e
  puts "Error when calling TransactionsApi->view_specific_transaction_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **transaction_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewSpecificTransaction**](ViewSpecificTransaction.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

