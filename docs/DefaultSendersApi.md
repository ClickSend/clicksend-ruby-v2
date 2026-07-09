# ClickSend::DefaultSendersApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_default_sender**](DefaultSendersApi.md#create_default_sender) | **POST** /v3/senders/default-senders | Create Default Sender |
| [**delete_default_sender**](DefaultSendersApi.md#delete_default_sender) | **DELETE** /v3/senders/default-senders/{default_sender_id} | Delete Default Sender |
| [**get_default_sender_details**](DefaultSendersApi.md#get_default_sender_details) | **GET** /v3/senders/default-senders/{default_sender_id} | Get Default Sender Details |
| [**get_default_senders_list**](DefaultSendersApi.md#get_default_senders_list) | **GET** /v3/senders/default-senders | Get List of Default Senders |
| [**list_compliant_sender_types**](DefaultSendersApi.md#list_compliant_sender_types) | **GET** /v3/senders/compliant-sender-types | List Compliant Sender Types |
| [**update_default_sender**](DefaultSendersApi.md#update_default_sender) | **PATCH** /v3/senders/default-senders/{default_sender_id} | Update Default Sender |


## create_default_sender

> <CreateDefaultSender> create_default_sender(opts)

Create Default Sender

Creates a new default sender configuration to automate the selection of compliant SenderIDs. By configuring a default sender you no longer need to define the `sender_id` string when sending SMS messages. The default sender will be picked up automatically.  For more information on Sender IDs, please refer to [What is a Sender ID or Sender Number?](https://help.clicksend.com/article/4kgj7krx00-what-is-a-sender-id-or-sender-number)

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

api_instance = ClickSend::DefaultSendersApi.new
opts = {
  content_type: 'application/json', # String | 
  create_default_sender_request: ClickSend::CreateDefaultSenderRequest.new({country_code: 'AU', product_type: 'SMS', default_sender_strategies: [ClickSend::CreateDefaultSenderRequestDefaultSenderStrategiesInner.new({sender_type: 'alpha_tag', sender_id: 'sender_id_example'})]}) # CreateDefaultSenderRequest | 
}

begin
  # Create Default Sender
  result = api_instance.create_default_sender(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling DefaultSendersApi->create_default_sender: #{e}"
end
```

#### Using the create_default_sender_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateDefaultSender>, Integer, Hash)> create_default_sender_with_http_info(opts)

```ruby
begin
  # Create Default Sender
  data, status_code, headers = api_instance.create_default_sender_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateDefaultSender>
rescue ClickSend::ApiError => e
  puts "Error when calling DefaultSendersApi->create_default_sender_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **create_default_sender_request** | [**CreateDefaultSenderRequest**](CreateDefaultSenderRequest.md) |  | [optional] |

### Return type

[**CreateDefaultSender**](CreateDefaultSender.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_default_sender

> delete_default_sender(default_sender_id, opts)

Delete Default Sender

Removes a specified default sender setting.  If you don't configure a default sender and leave the `sender_id` string blank when sending an SMS, Smart Assign will pick the best suitable, compliant, available SenderID for you.

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

api_instance = ClickSend::DefaultSendersApi.new
default_sender_id = 'default_sender_id_example' # String | The ID of the default sender to delete
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Delete Default Sender
  api_instance.delete_default_sender(default_sender_id, opts)
rescue ClickSend::ApiError => e
  puts "Error when calling DefaultSendersApi->delete_default_sender: #{e}"
end
```

#### Using the delete_default_sender_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_default_sender_with_http_info(default_sender_id, opts)

```ruby
begin
  # Delete Default Sender
  data, status_code, headers = api_instance.delete_default_sender_with_http_info(default_sender_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue ClickSend::ApiError => e
  puts "Error when calling DefaultSendersApi->delete_default_sender_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **default_sender_id** | **String** | The ID of the default sender to delete |  |
| **content_type** | **String** |  | [optional] |

### Return type

nil (empty response body)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## get_default_sender_details

> <GetDefaultSenderDetails> get_default_sender_details(default_sender_id, opts)

Get Default Sender Details

Retrieve detailed information about a specific default sender configuration

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

api_instance = ClickSend::DefaultSendersApi.new
default_sender_id = 'default_sender_id_example' # String | The ID of the default sender to retrieve
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Get Default Sender Details
  result = api_instance.get_default_sender_details(default_sender_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling DefaultSendersApi->get_default_sender_details: #{e}"
end
```

#### Using the get_default_sender_details_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetDefaultSenderDetails>, Integer, Hash)> get_default_sender_details_with_http_info(default_sender_id, opts)

```ruby
begin
  # Get Default Sender Details
  data, status_code, headers = api_instance.get_default_sender_details_with_http_info(default_sender_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetDefaultSenderDetails>
rescue ClickSend::ApiError => e
  puts "Error when calling DefaultSendersApi->get_default_sender_details_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **default_sender_id** | **String** | The ID of the default sender to retrieve |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**GetDefaultSenderDetails**](GetDefaultSenderDetails.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_default_senders_list

> <GetDefaultSendersList> get_default_senders_list(opts)

Get List of Default Senders

Retrieve a list of default senders for the current user

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

api_instance = ClickSend::DefaultSendersApi.new
opts = {
  content_type: 'application/json', # String | 
  offset: 'offset_example', # String | Page (offset) to be used for pagination
  per_page: 56, # Integer | Size of the page in pagination
  sort_by: 'sort_by_example', # String | Parameter to sort the results by
  sort_direction: 'asc' # String | Direction of sorting
}

begin
  # Get List of Default Senders
  result = api_instance.get_default_senders_list(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling DefaultSendersApi->get_default_senders_list: #{e}"
end
```

#### Using the get_default_senders_list_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetDefaultSendersList>, Integer, Hash)> get_default_senders_list_with_http_info(opts)

```ruby
begin
  # Get List of Default Senders
  data, status_code, headers = api_instance.get_default_senders_list_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetDefaultSendersList>
rescue ClickSend::ApiError => e
  puts "Error when calling DefaultSendersApi->get_default_senders_list_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **offset** | **String** | Page (offset) to be used for pagination | [optional] |
| **per_page** | **Integer** | Size of the page in pagination | [optional][default to 10] |
| **sort_by** | **String** | Parameter to sort the results by | [optional][default to &#39;created_timestamp&#39;] |
| **sort_direction** | **String** | Direction of sorting | [optional][default to &#39;desc&#39;] |

### Return type

[**GetDefaultSendersList**](GetDefaultSendersList.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_compliant_sender_types

> <ListCompliantSenderTypes200Response> list_compliant_sender_types(filter_product_type, opts)

List Compliant Sender Types

Retrieves the list of compliant sender types for specific countries

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

api_instance = ClickSend::DefaultSendersApi.new
filter_product_type = 'SMS' # String | Type of the product
opts = {
  filter_country_code_index: ['inner_example'] # Array<String> | Array of recipient country codes (ISO 3166-1 alpha-2). If not specified, will get all compliant sender types for all countries. Replace `{index}` with the appropriate index value.  <small>Example:</small> <small><code style=\"color: #424242;\">filter[country_code][0]=US&filter[country_code][1]=AU</code></small> 
}

begin
  # List Compliant Sender Types
  result = api_instance.list_compliant_sender_types(filter_product_type, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling DefaultSendersApi->list_compliant_sender_types: #{e}"
end
```

#### Using the list_compliant_sender_types_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListCompliantSenderTypes200Response>, Integer, Hash)> list_compliant_sender_types_with_http_info(filter_product_type, opts)

```ruby
begin
  # List Compliant Sender Types
  data, status_code, headers = api_instance.list_compliant_sender_types_with_http_info(filter_product_type, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListCompliantSenderTypes200Response>
rescue ClickSend::ApiError => e
  puts "Error when calling DefaultSendersApi->list_compliant_sender_types_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **filter_product_type** | **String** | Type of the product |  |
| **filter_country_code_index** | [**Array&lt;String&gt;**](String.md) | Array of recipient country codes (ISO 3166-1 alpha-2). If not specified, will get all compliant sender types for all countries. Replace &#x60;{index}&#x60; with the appropriate index value.  &lt;small&gt;Example:&lt;/small&gt; &lt;small&gt;&lt;code style&#x3D;\&quot;color: #424242;\&quot;&gt;filter[country_code][0]&#x3D;US&amp;filter[country_code][1]&#x3D;AU&lt;/code&gt;&lt;/small&gt;  | [optional] |

### Return type

[**ListCompliantSenderTypes200Response**](ListCompliantSenderTypes200Response.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_default_sender

> <UpdateDefaultSender> update_default_sender(default_sender_id, opts)

Update Default Sender

Updates the details of an existing default sender configuration.  For more information on Sender IDs, please refer to [What is a Sender ID or Sender Number?](https://help.clicksend.com/article/4kgj7krx00-what-is-a-sender-id-or-sender-number)

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

api_instance = ClickSend::DefaultSendersApi.new
default_sender_id = 'default_sender_id_example' # String | The ID of the default sender to update
opts = {
  content_type: 'application/json', # String | 
  update_default_sender_request: ClickSend::UpdateDefaultSenderRequest.new({default_sender_strategies: [ClickSend::CreateDefaultSenderRequestDefaultSenderStrategiesInner.new({sender_type: 'alpha_tag', sender_id: 'sender_id_example'})]}) # UpdateDefaultSenderRequest | 
}

begin
  # Update Default Sender
  result = api_instance.update_default_sender(default_sender_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling DefaultSendersApi->update_default_sender: #{e}"
end
```

#### Using the update_default_sender_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateDefaultSender>, Integer, Hash)> update_default_sender_with_http_info(default_sender_id, opts)

```ruby
begin
  # Update Default Sender
  data, status_code, headers = api_instance.update_default_sender_with_http_info(default_sender_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateDefaultSender>
rescue ClickSend::ApiError => e
  puts "Error when calling DefaultSendersApi->update_default_sender_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **default_sender_id** | **String** | The ID of the default sender to update |  |
| **content_type** | **String** |  | [optional] |
| **update_default_sender_request** | [**UpdateDefaultSenderRequest**](UpdateDefaultSenderRequest.md) |  | [optional] |

### Return type

[**UpdateDefaultSender**](UpdateDefaultSender.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

