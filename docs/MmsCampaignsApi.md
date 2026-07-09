# ClickSend::MmsCampaignsApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**calculate_mms_campaign_price**](MmsCampaignsApi.md#calculate_mms_campaign_price) | **POST** /v3/mms-campaigns/price | Calculate MMS Campaign Price |
| [**cancel_mms_campaign**](MmsCampaignsApi.md#cancel_mms_campaign) | **PUT** /v3/mms-campaigns/{mms_campaign_id}/cancel | Cancel MMS Campaign |
| [**send_mms_campaign**](MmsCampaignsApi.md#send_mms_campaign) | **POST** /v3/mms-campaigns/send | Send MMS Campaign |
| [**update_mms_campaign**](MmsCampaignsApi.md#update_mms_campaign) | **PUT** /v3/mms-campaigns/{mms_campaign_id} | Update MMS Campaign |
| [**view_all_mms_campaigns**](MmsCampaignsApi.md#view_all_mms_campaigns) | **GET** /v3/mms-campaigns | View All MMS Campaigns |
| [**view_mms_campaign**](MmsCampaignsApi.md#view_mms_campaign) | **GET** /v3/mms-campaigns/{mms_campaign_id} | View MMS Campaign |


## calculate_mms_campaign_price

> <CalculateMmsCampaignPrice> calculate_mms_campaign_price(opts)

Calculate MMS Campaign Price

_Calculate price for mms campaign_  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | list_id | integer(int32) | true | none | Your list id. | | name | string | true | none | Your campaign name. | | body | string | true | none | Your campaign message. | | from | string | true | [yes](http://help.clicksend.com/SMS/what-is-a-sender-id-or-sender-number) | Your sender id | | schedule | integer(int32) | false | none | Your schedule timestamp. | | subject | string | true | none | Subject of MMS campaign. | | media_file | string | true | none | URL pointing to media file. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::MmsCampaignsApi.new
opts = {
  content_type: 'application/json', # String | 
  body: { ... } # Object | 
}

begin
  # Calculate MMS Campaign Price
  result = api_instance.calculate_mms_campaign_price(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling MmsCampaignsApi->calculate_mms_campaign_price: #{e}"
end
```

#### Using the calculate_mms_campaign_price_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalculateMmsCampaignPrice>, Integer, Hash)> calculate_mms_campaign_price_with_http_info(opts)

```ruby
begin
  # Calculate MMS Campaign Price
  data, status_code, headers = api_instance.calculate_mms_campaign_price_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalculateMmsCampaignPrice>
rescue ClickSend::ApiError => e
  puts "Error when calling MmsCampaignsApi->calculate_mms_campaign_price_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **body** | **Object** |  | [optional] |

### Return type

[**CalculateMmsCampaignPrice**](CalculateMmsCampaignPrice.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## cancel_mms_campaign

> <CancelMmsCampaign> cancel_mms_campaign(mms_campaign_id, opts)

Cancel MMS Campaign

_Cancel mms campaign_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | mms_campaign_id | path | integer(int32) | true | ID of MMS Campaign to cancel |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::MmsCampaignsApi.new
mms_campaign_id = 'mms_campaign_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  calculate_sms_campaign_price_request: ClickSend::CalculateSmsCampaignPriceRequest.new # CalculateSmsCampaignPriceRequest | 
}

begin
  # Cancel MMS Campaign
  result = api_instance.cancel_mms_campaign(mms_campaign_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling MmsCampaignsApi->cancel_mms_campaign: #{e}"
end
```

#### Using the cancel_mms_campaign_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CancelMmsCampaign>, Integer, Hash)> cancel_mms_campaign_with_http_info(mms_campaign_id, opts)

```ruby
begin
  # Cancel MMS Campaign
  data, status_code, headers = api_instance.cancel_mms_campaign_with_http_info(mms_campaign_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CancelMmsCampaign>
rescue ClickSend::ApiError => e
  puts "Error when calling MmsCampaignsApi->cancel_mms_campaign_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **mms_campaign_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **calculate_sms_campaign_price_request** | [**CalculateSmsCampaignPriceRequest**](CalculateSmsCampaignPriceRequest.md) |  | [optional] |

### Return type

[**CancelMmsCampaign**](CancelMmsCampaign.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## send_mms_campaign

> <SendMmsCampaign> send_mms_campaign(opts)

Send MMS Campaign

_Create mms campaign_  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | list_id | integer(int32) | true | none | Your list id. | | name | string | true | none | Your campaign name. | | body | string | true | none | Your campaign message. | | from | string | true | [yes](http://help.clicksend.com/SMS/what-is-a-sender-id-or-sender-number) | Your sender id | | schedule | integer(int32) | false | none | Your schedule timestamp. | | subject | string | true | none | Subject of MMS campaign. | | media_file | string | true | none | URL pointing to media file. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::MmsCampaignsApi.new
opts = {
  content_type: 'application/json', # String | 
  send_mms_campaign_request: ClickSend::SendMmsCampaignRequest.new # SendMmsCampaignRequest | 
}

begin
  # Send MMS Campaign
  result = api_instance.send_mms_campaign(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling MmsCampaignsApi->send_mms_campaign: #{e}"
end
```

#### Using the send_mms_campaign_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendMmsCampaign>, Integer, Hash)> send_mms_campaign_with_http_info(opts)

```ruby
begin
  # Send MMS Campaign
  data, status_code, headers = api_instance.send_mms_campaign_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendMmsCampaign>
rescue ClickSend::ApiError => e
  puts "Error when calling MmsCampaignsApi->send_mms_campaign_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **send_mms_campaign_request** | [**SendMmsCampaignRequest**](SendMmsCampaignRequest.md) |  | [optional] |

### Return type

[**SendMmsCampaign**](SendMmsCampaign.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_mms_campaign

> <UpdateMmsCampaign> update_mms_campaign(mms_campaign_id, opts)

Update MMS Campaign

_Update mms campaign_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | mms_campaign_id | path | integer(int32) | true | ID of MMS campaign to update |  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | list_id | integer(int32) | true | none | Your list id. | | name | string | true | none | Your campaign name. | | body | string | true | none | Your campaign message. | | from | string | true | [yes](http://help.clicksend.com/SMS/what-is-a-sender-id-or-sender-number) | Your sender id | | schedule | integer(int32) | false | none | Your schedule timestamp. | | subject | string | true | none | Subject of MMS campaign. | | media_file | string | true | none | URL pointing to media file. |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::MmsCampaignsApi.new
mms_campaign_id = 'mms_campaign_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  calculate_sms_campaign_price_request: ClickSend::CalculateSmsCampaignPriceRequest.new # CalculateSmsCampaignPriceRequest | 
}

begin
  # Update MMS Campaign
  result = api_instance.update_mms_campaign(mms_campaign_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling MmsCampaignsApi->update_mms_campaign: #{e}"
end
```

#### Using the update_mms_campaign_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateMmsCampaign>, Integer, Hash)> update_mms_campaign_with_http_info(mms_campaign_id, opts)

```ruby
begin
  # Update MMS Campaign
  data, status_code, headers = api_instance.update_mms_campaign_with_http_info(mms_campaign_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateMmsCampaign>
rescue ClickSend::ApiError => e
  puts "Error when calling MmsCampaignsApi->update_mms_campaign_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **mms_campaign_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **calculate_sms_campaign_price_request** | [**CalculateSmsCampaignPriceRequest**](CalculateSmsCampaignPriceRequest.md) |  | [optional] |

### Return type

[**UpdateMmsCampaign**](UpdateMmsCampaign.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## view_all_mms_campaigns

> <ViewAllMmsCampaigns> view_all_mms_campaigns(opts)

View All MMS Campaigns

_Get list of mms campaigns_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | page | query | integer(int32) | false | [Page number](/#pagination) | | limit | query | integer(int32) | false | [Number of records per page](/#pagination) |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::MmsCampaignsApi.new
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View All MMS Campaigns
  result = api_instance.view_all_mms_campaigns(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling MmsCampaignsApi->view_all_mms_campaigns: #{e}"
end
```

#### Using the view_all_mms_campaigns_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewAllMmsCampaigns>, Integer, Hash)> view_all_mms_campaigns_with_http_info(opts)

```ruby
begin
  # View All MMS Campaigns
  data, status_code, headers = api_instance.view_all_mms_campaigns_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewAllMmsCampaigns>
rescue ClickSend::ApiError => e
  puts "Error when calling MmsCampaignsApi->view_all_mms_campaigns_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewAllMmsCampaigns**](ViewAllMmsCampaigns.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_mms_campaign

> <ViewMmsCampaign> view_mms_campaign(mms_campaign_id, opts)

View MMS Campaign

_Get specific mms campaign_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | mms_campaign_id | path | integer(int32) | true | ID of MMS campaign to retrieve |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::MmsCampaignsApi.new
mms_campaign_id = 'mms_campaign_id_example' # String | 
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View MMS Campaign
  result = api_instance.view_mms_campaign(mms_campaign_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling MmsCampaignsApi->view_mms_campaign: #{e}"
end
```

#### Using the view_mms_campaign_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewMmsCampaign>, Integer, Hash)> view_mms_campaign_with_http_info(mms_campaign_id, opts)

```ruby
begin
  # View MMS Campaign
  data, status_code, headers = api_instance.view_mms_campaign_with_http_info(mms_campaign_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewMmsCampaign>
rescue ClickSend::ApiError => e
  puts "Error when calling MmsCampaignsApi->view_mms_campaign_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **mms_campaign_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewMmsCampaign**](ViewMmsCampaign.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

