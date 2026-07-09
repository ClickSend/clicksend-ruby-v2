# ClickSend::AlphaTagsApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**delete_alpha_tag**](AlphaTagsApi.md#delete_alpha_tag) | **DELETE** /v3/alpha-tags/{alpha_tag_id} | Delete Alpha Tag |
| [**get_alpha_tag**](AlphaTagsApi.md#get_alpha_tag) | **GET** /v3/alpha-tags/{alpha_tag_id} | Get Alpha Tag |
| [**list_alpha_tags**](AlphaTagsApi.md#list_alpha_tags) | **GET** /v3/alpha-tags | List Alpha Tags |
| [**request_alpha_tag**](AlphaTagsApi.md#request_alpha_tag) | **POST** /v3/alpha-tags | Request Alpha Tag |


## delete_alpha_tag

> delete_alpha_tag(alpha_tag_id, opts)

Delete Alpha Tag

_Delete a specific alpha tag._  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | alpha_tag_id | path | uuid | true | ID of the alpha tag |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  This endpoint requires authentication, [more info...](/#authentication)

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

api_instance = ClickSend::AlphaTagsApi.new
alpha_tag_id = 'alpha_tag_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Delete Alpha Tag
  api_instance.delete_alpha_tag(alpha_tag_id, opts)
rescue ClickSend::ApiError => e
  puts "Error when calling AlphaTagsApi->delete_alpha_tag: #{e}"
end
```

#### Using the delete_alpha_tag_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_alpha_tag_with_http_info(alpha_tag_id, opts)

```ruby
begin
  # Delete Alpha Tag
  data, status_code, headers = api_instance.delete_alpha_tag_with_http_info(alpha_tag_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue ClickSend::ApiError => e
  puts "Error when calling AlphaTagsApi->delete_alpha_tag_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **alpha_tag_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

nil (empty response body)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_alpha_tag

> <AlphaTag> get_alpha_tag(alpha_tag_id, opts)

Get Alpha Tag

_Get a specific alpha tag._  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | alpha_tag_id | path | uuid | true | ID of the alpha tag |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   This endpoint requires authentication, [more info...](/#authentication)

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

api_instance = ClickSend::AlphaTagsApi.new
alpha_tag_id = 'alpha_tag_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Get Alpha Tag
  result = api_instance.get_alpha_tag(alpha_tag_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling AlphaTagsApi->get_alpha_tag: #{e}"
end
```

#### Using the get_alpha_tag_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AlphaTag>, Integer, Hash)> get_alpha_tag_with_http_info(alpha_tag_id, opts)

```ruby
begin
  # Get Alpha Tag
  data, status_code, headers = api_instance.get_alpha_tag_with_http_info(alpha_tag_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AlphaTag>
rescue ClickSend::ApiError => e
  puts "Error when calling AlphaTagsApi->get_alpha_tag_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **alpha_tag_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**AlphaTag**](AlphaTag.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_alpha_tags

> <ListAlphaTags> list_alpha_tags(opts)

List Alpha Tags



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

api_instance = ClickSend::AlphaTagsApi.new
opts = {
  sort_direction: 'asc', # String | The sort direction for the results. The default value is asc.
  page_size: 10 # Integer | The number of items to return per page. This parameter controls the size of each page of results. The default value is 10.
}

begin
  # List Alpha Tags
  result = api_instance.list_alpha_tags(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling AlphaTagsApi->list_alpha_tags: #{e}"
end
```

#### Using the list_alpha_tags_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListAlphaTags>, Integer, Hash)> list_alpha_tags_with_http_info(opts)

```ruby
begin
  # List Alpha Tags
  data, status_code, headers = api_instance.list_alpha_tags_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListAlphaTags>
rescue ClickSend::ApiError => e
  puts "Error when calling AlphaTagsApi->list_alpha_tags_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **sort_direction** | **String** | The sort direction for the results. The default value is asc. | [optional][default to &#39;asc&#39;] |
| **page_size** | **Integer** | The number of items to return per page. This parameter controls the size of each page of results. The default value is 10. | [optional][default to 10] |

### Return type

[**ListAlphaTags**](ListAlphaTags.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## request_alpha_tag

> <AlphaTag> request_alpha_tag(opts)

Request Alpha Tag

_Request to register an alpha tag. After requested, the alpha tag will be reviewed by ClickSend and either approved or rejected. Some countries (e.g Australia) require you to submit additional fields due to government mandated compliance checks._  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | alpha_tag | string | true | [yes](https://help.clicksend.com/article/1qxfxkcwm2-global-generic-alpha-tags) | The alpha tag name. Length must be between 3 - 11 characters, can only contain a-z A-Z 0-9 + and must contain at least one non numeric. | | reason | string | false | none | Must be one of the following: `Sole Trader Name`, `Company Name`, `Partnership Name`, `Registered Trust Name`, `Co-Operative Name`, `Indigenous Corporation Name`, `Registered Organisation Name`, `Personal Name`, `Trademark`, `Government Agency or Entity`, `Product or Service Name`, `Acronym/Initialism`, `Contraction of Name`, `Third Party`. In case of `Third Party`, we will contact you to collect the relevant information. | | countries | array of strings | false | none | List of country codes (e.g., \"AU\", \"US\") where the alpha tag is requested. Only supported and required for AU. | | businesses | array of objects | false | none | List of business details required for alpha tag registration. Each object contains country, business information, ... Required if `countries` is provided. When `business_relationship` is `ENTITY_ASSOCIATE`, the following partner fields are also **required**: `partner_business_name`, `partner_abn`, `partner_business_info`, `partner_business_address`, `partner_representative`. These fields are **forbidden** for any other `business_relationship` value. |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  _This endpoint requires authentication,_ [more info...](/#authentication) 

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

api_instance = ClickSend::AlphaTagsApi.new
opts = {
  content_type: 'application/json', # String | 
  request_alpha_tag_request: ClickSend::RequestAlphaTagRequest.new # RequestAlphaTagRequest | 
}

begin
  # Request Alpha Tag
  result = api_instance.request_alpha_tag(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling AlphaTagsApi->request_alpha_tag: #{e}"
end
```

#### Using the request_alpha_tag_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AlphaTag>, Integer, Hash)> request_alpha_tag_with_http_info(opts)

```ruby
begin
  # Request Alpha Tag
  data, status_code, headers = api_instance.request_alpha_tag_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AlphaTag>
rescue ClickSend::ApiError => e
  puts "Error when calling AlphaTagsApi->request_alpha_tag_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **request_alpha_tag_request** | [**RequestAlphaTagRequest**](RequestAlphaTagRequest.md) |  | [optional] |

### Return type

[**AlphaTag**](AlphaTag.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

