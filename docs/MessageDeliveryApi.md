# ClickSend::MessageDeliveryApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_delivery_issue**](MessageDeliveryApi.md#create_delivery_issue) | **POST** /v3/delivery-issues | Create Delivery Issues |
| [**get_all_delivery_issues**](MessageDeliveryApi.md#get_all_delivery_issues) | **GET** /v3/delivery-issues | Get All Delivery Issues |


## create_delivery_issue

> <CreateDeliveryIssue> create_delivery_issue(opts)

Create Delivery Issues

_Create delivery Issue_  Create delivery Issue  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | message_id | string | false | none | The message id of the message. | | type | string | true | none | The type of message, must be one of the following values SMS, MMS, VOICE, EMAIL_MARKETING, EMAIL_TRANSACTIONAL, FAX, POST. | | description | string | true | none | The description of the message. | | client_comments | string | false | none | The user's comments. | | email-address | string | true | none | The user's email address. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::MessageDeliveryApi.new
opts = {
  content_type: 'application/json', # String | 
  create_delivery_issue_request: ClickSend::CreateDeliveryIssueRequest.new # CreateDeliveryIssueRequest | 
}

begin
  # Create Delivery Issues
  result = api_instance.create_delivery_issue(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling MessageDeliveryApi->create_delivery_issue: #{e}"
end
```

#### Using the create_delivery_issue_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateDeliveryIssue>, Integer, Hash)> create_delivery_issue_with_http_info(opts)

```ruby
begin
  # Create Delivery Issues
  data, status_code, headers = api_instance.create_delivery_issue_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateDeliveryIssue>
rescue ClickSend::ApiError => e
  puts "Error when calling MessageDeliveryApi->create_delivery_issue_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **create_delivery_issue_request** | [**CreateDeliveryIssueRequest**](CreateDeliveryIssueRequest.md) |  | [optional] |

### Return type

[**CreateDeliveryIssue**](CreateDeliveryIssue.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_all_delivery_issues

> <GetAllDeliveryIssues> get_all_delivery_issues(opts)

Get All Delivery Issues

_Get all delivery issues_  Get all delivery issues  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | Page number | | limit | query | integer(int32) | false | Number of records per page |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::MessageDeliveryApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Get All Delivery Issues
  result = api_instance.get_all_delivery_issues(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling MessageDeliveryApi->get_all_delivery_issues: #{e}"
end
```

#### Using the get_all_delivery_issues_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetAllDeliveryIssues>, Integer, Hash)> get_all_delivery_issues_with_http_info(opts)

```ruby
begin
  # Get All Delivery Issues
  data, status_code, headers = api_instance.get_all_delivery_issues_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetAllDeliveryIssues>
rescue ClickSend::ApiError => e
  puts "Error when calling MessageDeliveryApi->get_all_delivery_issues_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**GetAllDeliveryIssues**](GetAllDeliveryIssues.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

