# ClickSend::VerificationApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**forgot_password**](VerificationApi.md#forgot_password) | **PUT** /v3/forgot-password | Forgot Password |
| [**forgot_username**](VerificationApi.md#forgot_username) | **PUT** /v3/forgot-username | Forgot Username |


## forgot_password

> <ForgotPassword> forgot_password(opts)

Forgot Password

_Forgot password_  A user can send their username to this endpoint to be sent an email with their registered email address that will have a verification code.  Once you have this verification email containing the code you can send it to the [forgotten-password/verify](/#verify-forgot-password) endpoint along with a new password and the ID of that subaccount.  _Ask your administrator if you do not know your subaccount id._  ### Properties  | **Name** | **Type** | **Required** | **Restrictions** | **Description** | | --- | --- | --- | --- | --- | | username | string | true | none | Username belonging to account |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #6BBD5B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint does not require authentication</span>  </div>

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

api_instance = ClickSend::VerificationApi.new
opts = {
  content_type: 'application/json', # String | 
  forgot_password_request: ClickSend::ForgotPasswordRequest.new # ForgotPasswordRequest | 
}

begin
  # Forgot Password
  result = api_instance.forgot_password(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling VerificationApi->forgot_password: #{e}"
end
```

#### Using the forgot_password_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ForgotPassword>, Integer, Hash)> forgot_password_with_http_info(opts)

```ruby
begin
  # Forgot Password
  data, status_code, headers = api_instance.forgot_password_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ForgotPassword>
rescue ClickSend::ApiError => e
  puts "Error when calling VerificationApi->forgot_password_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **forgot_password_request** | [**ForgotPasswordRequest**](ForgotPasswordRequest.md) |  | [optional] |

### Return type

[**ForgotPassword**](ForgotPassword.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## forgot_username

> <ForgotUsername> forgot_username(opts)

Forgot Username

_Forgot username_  Requires the user to pass either the email registered to an account or the phone number, **not** both  ### Properties  | **Name** | **Type** | **Required** | **Restrictions** | **Description** | | --- | --- | --- | --- | --- | | email | string | true | none | Email belonging to account | | phone_number | string | true | none | Phone belonging to account |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #6BBD5B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint does not require authentication</span>  </div>   

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

api_instance = ClickSend::VerificationApi.new
opts = {
  content_type: 'application/json', # String | 
  forgot_username_request: ClickSend::ForgotUsernameRequest.new # ForgotUsernameRequest | 
}

begin
  # Forgot Username
  result = api_instance.forgot_username(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling VerificationApi->forgot_username: #{e}"
end
```

#### Using the forgot_username_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ForgotUsername>, Integer, Hash)> forgot_username_with_http_info(opts)

```ruby
begin
  # Forgot Username
  data, status_code, headers = api_instance.forgot_username_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ForgotUsername>
rescue ClickSend::ApiError => e
  puts "Error when calling VerificationApi->forgot_username_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **forgot_username_request** | [**ForgotUsernameRequest**](ForgotUsernameRequest.md) |  | [optional] |

### Return type

[**ForgotUsername**](ForgotUsername.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

