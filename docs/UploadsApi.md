# ClickSend::UploadsApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**upload_a_media_file**](UploadsApi.md#upload_a_media_file) | **POST** /v3/uploads | Upload Media File |


## upload_a_media_file

> upload_a_media_file(opts)

Upload Media File

The `upload` endpoint provides a method for converting files from an unsupported format to a format that one of our endpoints can handle.  Files can be submitted two ways: 1. Using `base64` encoding in an `application/json` request. In this case, submit the `base64`\\-encoded file contents in the `content` field of the request body, and `convert` can be specified either also in the body or as part of the query string. 2. Using `multipart/form-data` encoding, in the same way it would be submitted using a HTML form. You may find cURL useful for this. For an example of how to do this, see one of our [SDKs](https://dashboard.clicksend.com/#/libraries-sdk/main). In this case, specify `convert` in the query string.  Note that `convert` specifies the conversion to take place. That is, what the result should be compatible with and can be any of the following:  - `fax` - `mms` - `csv` - `post` - `postcard`       All files will expire 10 minutes after being uploaded.  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | convert | query | string | true | none | | content | body | string | true | Base64-encoded file contents |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  This endpoint requires authentication, [more info...](/#authentication)

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

api_instance = ClickSend::UploadsApi.new
opts = {
  content_type: 'application/json', # String | 
  body: { ... } # Object | 
}

begin
  # Upload Media File
  api_instance.upload_a_media_file(opts)
rescue ClickSend::ApiError => e
  puts "Error when calling UploadsApi->upload_a_media_file: #{e}"
end
```

#### Using the upload_a_media_file_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> upload_a_media_file_with_http_info(opts)

```ruby
begin
  # Upload Media File
  data, status_code, headers = api_instance.upload_a_media_file_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue ClickSend::ApiError => e
  puts "Error when calling UploadsApi->upload_a_media_file_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **body** | **Object** |  | [optional] |

### Return type

nil (empty response body)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

