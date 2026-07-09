# ClickSend::ReferralsApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**view_referral_accounts**](ReferralsApi.md#view_referral_accounts) | **GET** /v3/referral/accounts/ | View Referral Accounts |


## view_referral_accounts

> <ViewReferralAccounts> view_referral_accounts(opts)

View Referral Accounts

_Get all referral accounts_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::ReferralsApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Referral Accounts
  result = api_instance.view_referral_accounts(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling ReferralsApi->view_referral_accounts: #{e}"
end
```

#### Using the view_referral_accounts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewReferralAccounts>, Integer, Hash)> view_referral_accounts_with_http_info(opts)

```ruby
begin
  # View Referral Accounts
  data, status_code, headers = api_instance.view_referral_accounts_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewReferralAccounts>
rescue ClickSend::ApiError => e
  puts "Error when calling ReferralsApi->view_referral_accounts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewReferralAccounts**](ViewReferralAccounts.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

