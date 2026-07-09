# ClickSend::SmsCampaignsApi

All URIs are relative to *https://rest.clicksend.com*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**calculate_sms_campaign_price**](SmsCampaignsApi.md#calculate_sms_campaign_price) | **POST** /v3/sms-campaigns/price | Calculate SMS Campaign Price |
| [**cancel_sms_campaign**](SmsCampaignsApi.md#cancel_sms_campaign) | **PUT** /v3/sms-campaigns/{sms_campaign_id}/cancel | Cancel SMS Campaign |
| [**send_sms_campaign**](SmsCampaignsApi.md#send_sms_campaign) | **POST** /v3/sms-campaigns/send | Send SMS Campaign |
| [**update_sms_campaign**](SmsCampaignsApi.md#update_sms_campaign) | **PUT** /v3/sms-campaigns/{sms_campaign_id} | Update SMS Campaign |
| [**view_sms_campaigns**](SmsCampaignsApi.md#view_sms_campaigns) | **GET** /v3/sms-campaigns | View SMS Campaigns |
| [**view_specific_sms_campaign**](SmsCampaignsApi.md#view_specific_sms_campaign) | **GET** /v3/sms-campaigns/{sms_campaign_id} | View Specific SMS Campaign |


## calculate_sms_campaign_price

> <CalculateSmsCampaignPrice> calculate_sms_campaign_price(opts)

Calculate SMS Campaign Price

_Calculate price for sms campaign_  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | list_id | integer(int32) | true | none | Your list id. | | name | string | true | none | Your campaign name. | | body | string | true | none | Your campaign message. | | from | string | true | [yes](http://help.clicksend.com/SMS/what-is-a-sender-id-or-sender-number) | Your sender id | | schedule | integer(int32) | false | none | Your schedule timestamp. |   Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.   <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SmsCampaignsApi.new
opts = {
  content_type: 'application/json', # String | 
  calculate_sms_campaign_price_request: ClickSend::CalculateSmsCampaignPriceRequest.new # CalculateSmsCampaignPriceRequest | 
}

begin
  # Calculate SMS Campaign Price
  result = api_instance.calculate_sms_campaign_price(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsCampaignsApi->calculate_sms_campaign_price: #{e}"
end
```

#### Using the calculate_sms_campaign_price_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CalculateSmsCampaignPrice>, Integer, Hash)> calculate_sms_campaign_price_with_http_info(opts)

```ruby
begin
  # Calculate SMS Campaign Price
  data, status_code, headers = api_instance.calculate_sms_campaign_price_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CalculateSmsCampaignPrice>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsCampaignsApi->calculate_sms_campaign_price_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **calculate_sms_campaign_price_request** | [**CalculateSmsCampaignPriceRequest**](CalculateSmsCampaignPriceRequest.md) |  | [optional] |

### Return type

[**CalculateSmsCampaignPrice**](CalculateSmsCampaignPrice.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## cancel_sms_campaign

> <CancelSmsCampaign> cancel_sms_campaign(sms_campaign_id, opts)

Cancel SMS Campaign

Use this endpoint to cancel a scheduled SMS campaign.

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

api_instance = ClickSend::SmsCampaignsApi.new
sms_campaign_id = 'sms_campaign_id_example' # String | ID of the scheduled SMS campaign to cancel.
opts = {
  content_type: 'application/json' # String | 
}

begin
  # Cancel SMS Campaign
  result = api_instance.cancel_sms_campaign(sms_campaign_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsCampaignsApi->cancel_sms_campaign: #{e}"
end
```

#### Using the cancel_sms_campaign_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CancelSmsCampaign>, Integer, Hash)> cancel_sms_campaign_with_http_info(sms_campaign_id, opts)

```ruby
begin
  # Cancel SMS Campaign
  data, status_code, headers = api_instance.cancel_sms_campaign_with_http_info(sms_campaign_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CancelSmsCampaign>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsCampaignsApi->cancel_sms_campaign_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **sms_campaign_id** | **String** | ID of the scheduled SMS campaign to cancel. |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**CancelSmsCampaign**](CancelSmsCampaign.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## send_sms_campaign

> <SendSmsCampaign> send_sms_campaign(opts)

Send SMS Campaign

### _SMS Campaign Endpoint_  You can post to a list with `up to 20000 recipients` with each API call. You can only send to a single list containing up to 20,000 recipients. The response is far less detailed than the normal Send SMS endpoint. Use the [SMS Send](/#send-sms) endpoint if you would like to send to less than 1000 recipients at once. You are required to add an opt-out message to the end of your message body if you are sending marketing message. This can be in the form of asking users to reply STOP to opt-out or by including `StopMsg.me/xxxxx` which is a placeholder that will add a link that can be clicked to out-out. Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses. <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SmsCampaignsApi.new
opts = {
  content_type: 'application/json', # String | 
  send_sms_campaign_request: ClickSend::SendSmsCampaignRequest.new({list_id: 1, name: 'My Campaign', from: 'from_example', body: 'body_example', senders: [ClickSend::SendersInner.new({recipient_country_code: 'recipient_country_code_example'})]}) # SendSmsCampaignRequest | 
}

begin
  # Send SMS Campaign
  result = api_instance.send_sms_campaign(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsCampaignsApi->send_sms_campaign: #{e}"
end
```

#### Using the send_sms_campaign_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SendSmsCampaign>, Integer, Hash)> send_sms_campaign_with_http_info(opts)

```ruby
begin
  # Send SMS Campaign
  data, status_code, headers = api_instance.send_sms_campaign_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SendSmsCampaign>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsCampaignsApi->send_sms_campaign_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **send_sms_campaign_request** | [**SendSmsCampaignRequest**](SendSmsCampaignRequest.md) |  | [optional] |

### Return type

[**SendSmsCampaign**](SendSmsCampaign.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_sms_campaign

> <UpdateSmsCampaign> update_sms_campaign(sms_campaign_id, opts)

Update SMS Campaign

_Update sms campaign_  ### Parameters  | Parameter | In | Type | Required | Description | | --- | --- | --- | --- | --- | | sms_campaign_id | path | integer(int32) | true | ID of SMS campaign to update |  ### Properties  | Name | Type | Required | Restrictions | Description | | --- | --- | --- | --- | --- | | list_id | integer(int32) | true | none | Your list id. | | name | string | true | none | Your campaign name. | | body | string | true | none | Your campaign message. | | from | string | true | [yes](http://help.clicksend.com/SMS/what-is-a-sender-id-or-sender-number) | Your sender id | | schedule | integer(int32) | false | none | Your schedule timestamp. |  Refer to [Status Codes](/#status-codes) for definitions of HTTP status code responses.  <div style=\"background-color: #FF6A4B; padding: 10px; border-radius: 8px;\">   <span style=\"color: white;\">This endpoint requires authentication,</span>    <a href=\"/docs/#authentication\" style=\"color: white; text-decoration: underline;\">more info...</a> </div>

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

api_instance = ClickSend::SmsCampaignsApi.new
sms_campaign_id = 'sms_campaign_id_example' # String | 
opts = {
  content_type: 'application/json', # String | 
  calculate_sms_campaign_price_request: ClickSend::CalculateSmsCampaignPriceRequest.new # CalculateSmsCampaignPriceRequest | 
}

begin
  # Update SMS Campaign
  result = api_instance.update_sms_campaign(sms_campaign_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsCampaignsApi->update_sms_campaign: #{e}"
end
```

#### Using the update_sms_campaign_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateSmsCampaign>, Integer, Hash)> update_sms_campaign_with_http_info(sms_campaign_id, opts)

```ruby
begin
  # Update SMS Campaign
  data, status_code, headers = api_instance.update_sms_campaign_with_http_info(sms_campaign_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateSmsCampaign>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsCampaignsApi->update_sms_campaign_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **sms_campaign_id** | **String** |  |  |
| **content_type** | **String** |  | [optional] |
| **calculate_sms_campaign_price_request** | [**CalculateSmsCampaignPriceRequest**](CalculateSmsCampaignPriceRequest.md) |  | [optional] |

### Return type

[**UpdateSmsCampaign**](UpdateSmsCampaign.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## view_sms_campaigns

> <ViewSmsCampaigns> view_sms_campaigns(opts)

View SMS Campaigns

Use this endpoint to view SMS campaigns.

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

api_instance = ClickSend::SmsCampaignsApi.new
opts = {
  content_type: 'application/json', # String | 
  page: 1, # Integer | The page number to retrieve. Use this parameter to navigate through the [pagination]/#pagination) results. The default value is 1.
  limit: 56, # Integer | The number of items to return per page. This parameter controls the size of each page of results. The default value is 15.
  q: 'q_example', # String | Allows filtering of results based on your search criteria. The query should be in the format `field_name:value`.  1. **Field Name**: The field within the SMS campaign you want to filter by. You can use the following fields:      - sms_campaign_id,name,user_id,subaccount_id,list_id,from,body,schedule,status,date_added,custom_string,url_to_shorten,unsubscribe_link,source   2. **Value**: The text or keyword you're searching for within the specified field. If left empty after the colon, the filter will look for all templates with any value in the **Field Name**.  For example, if you are searching for a SMS campaign with the status of _Scheduled_, the final query would look like this:    - `q=status:Scheduled`  <div class=\"info-box\">   <h4><i class=\"fas fa-info-circle\"></i> Note:</h4>   <p>   Some characters have to be encoded. For example, if you are searching for SMS sent from the phone number +61437085284, your search query q would be:<br/>    <ul>     <li>q=from:%2B61437085284</li>   </ul>    You can use the <a href=\"https://www.urlencoder.org/\" target=\"_blank\">URL encoder</a> to encode the text. If a character is not an alphanumeric character (A-Z, a-z, 0-9), it is typically either reserved or unsafe and should be encoded.      </p> </div>
  order_by: 'order_by_example', # String | Specifies the field and order to sort the results by. The value is composed of the field name followed by a colon and the sort direction (_asc_ for ascending or _desc_ for descending).  The default sort order is by _date_added_ in ascending order. You can use the following fields:    - _name_: The name of the SMS campaign.   - _status_: The status of the SMS campaign.   - _schedule_: The schedule send date of the SMS campaign in the <a href=\"http://help.clicksend.com/what-is-a-unix-timestamp\" target=\"_blank\">Unix format</a>.   - _from_: The sender of the SMS campaign.   - _date_added_: This is the date you created or updated the SMS campaign in the <a href=\"http://help.clicksend.com/what-is-a-unix-timestamp\" target=\"_blank\">Unix format</a>.  For example, if you want to order by the most recently sent or scheduled SMS, you should sort by date in descending order. The query would look like this:    - `order_by=schedule:desc`  <div class=\"info-box\">   <h4><i class=\"fas fa-info-circle\"></i> Note:</h4>   <p>     You can also sort by these fields: <br/>     <ul>     <li>sms_campaign_id,user_id,subaccount_id,list_id,body,custom_string,url_to_shorten,unsubscribe_link, and source.</li>   </ul>   <br/>   But this is less common in practice.   </p> </div>
  date_from: 56, # Integer | Start date to filter results. It should be in <a href=\"http://help.clicksend.com/what-is-a-unix-timestamp\" target=\"_blank\">Unix format</a>.
  date_to: 56 # Integer | End date to filter results. It should be in <a href=\"http://help.clicksend.com/what-is-a-unix-timestamp\" target=\"_blank\">Unix format</a>.
}

begin
  # View SMS Campaigns
  result = api_instance.view_sms_campaigns(opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsCampaignsApi->view_sms_campaigns: #{e}"
end
```

#### Using the view_sms_campaigns_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewSmsCampaigns>, Integer, Hash)> view_sms_campaigns_with_http_info(opts)

```ruby
begin
  # View SMS Campaigns
  data, status_code, headers = api_instance.view_sms_campaigns_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewSmsCampaigns>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsCampaignsApi->view_sms_campaigns_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **content_type** | **String** |  | [optional] |
| **page** | **Integer** | The page number to retrieve. Use this parameter to navigate through the [pagination]/#pagination) results. The default value is 1. | [optional][default to 1] |
| **limit** | **Integer** | The number of items to return per page. This parameter controls the size of each page of results. The default value is 15. | [optional][default to 15] |
| **q** | **String** | Allows filtering of results based on your search criteria. The query should be in the format &#x60;field_name:value&#x60;.  1. **Field Name**: The field within the SMS campaign you want to filter by. You can use the following fields:      - sms_campaign_id,name,user_id,subaccount_id,list_id,from,body,schedule,status,date_added,custom_string,url_to_shorten,unsubscribe_link,source   2. **Value**: The text or keyword you&#39;re searching for within the specified field. If left empty after the colon, the filter will look for all templates with any value in the **Field Name**.  For example, if you are searching for a SMS campaign with the status of _Scheduled_, the final query would look like this:    - &#x60;q&#x3D;status:Scheduled&#x60;  &lt;div class&#x3D;\&quot;info-box\&quot;&gt;   &lt;h4&gt;&lt;i class&#x3D;\&quot;fas fa-info-circle\&quot;&gt;&lt;/i&gt; Note:&lt;/h4&gt;   &lt;p&gt;   Some characters have to be encoded. For example, if you are searching for SMS sent from the phone number +61437085284, your search query q would be:&lt;br/&gt;    &lt;ul&gt;     &lt;li&gt;q&#x3D;from:%2B61437085284&lt;/li&gt;   &lt;/ul&gt;    You can use the &lt;a href&#x3D;\&quot;https://www.urlencoder.org/\&quot; target&#x3D;\&quot;_blank\&quot;&gt;URL encoder&lt;/a&gt; to encode the text. If a character is not an alphanumeric character (A-Z, a-z, 0-9), it is typically either reserved or unsafe and should be encoded.      &lt;/p&gt; &lt;/div&gt; | [optional] |
| **order_by** | **String** | Specifies the field and order to sort the results by. The value is composed of the field name followed by a colon and the sort direction (_asc_ for ascending or _desc_ for descending).  The default sort order is by _date_added_ in ascending order. You can use the following fields:    - _name_: The name of the SMS campaign.   - _status_: The status of the SMS campaign.   - _schedule_: The schedule send date of the SMS campaign in the &lt;a href&#x3D;\&quot;http://help.clicksend.com/what-is-a-unix-timestamp\&quot; target&#x3D;\&quot;_blank\&quot;&gt;Unix format&lt;/a&gt;.   - _from_: The sender of the SMS campaign.   - _date_added_: This is the date you created or updated the SMS campaign in the &lt;a href&#x3D;\&quot;http://help.clicksend.com/what-is-a-unix-timestamp\&quot; target&#x3D;\&quot;_blank\&quot;&gt;Unix format&lt;/a&gt;.  For example, if you want to order by the most recently sent or scheduled SMS, you should sort by date in descending order. The query would look like this:    - &#x60;order_by&#x3D;schedule:desc&#x60;  &lt;div class&#x3D;\&quot;info-box\&quot;&gt;   &lt;h4&gt;&lt;i class&#x3D;\&quot;fas fa-info-circle\&quot;&gt;&lt;/i&gt; Note:&lt;/h4&gt;   &lt;p&gt;     You can also sort by these fields: &lt;br/&gt;     &lt;ul&gt;     &lt;li&gt;sms_campaign_id,user_id,subaccount_id,list_id,body,custom_string,url_to_shorten,unsubscribe_link, and source.&lt;/li&gt;   &lt;/ul&gt;   &lt;br/&gt;   But this is less common in practice.   &lt;/p&gt; &lt;/div&gt; | [optional] |
| **date_from** | **Integer** | Start date to filter results. It should be in &lt;a href&#x3D;\&quot;http://help.clicksend.com/what-is-a-unix-timestamp\&quot; target&#x3D;\&quot;_blank\&quot;&gt;Unix format&lt;/a&gt;. | [optional] |
| **date_to** | **Integer** | End date to filter results. It should be in &lt;a href&#x3D;\&quot;http://help.clicksend.com/what-is-a-unix-timestamp\&quot; target&#x3D;\&quot;_blank\&quot;&gt;Unix format&lt;/a&gt;. | [optional] |

### Return type

[**ViewSmsCampaigns**](ViewSmsCampaigns.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## view_specific_sms_campaign

> <ViewSpecificSmsCampaign> view_specific_sms_campaign(sms_campaign_id, opts)

View Specific SMS Campaign

Use this endpoint to view a specific SMS campaign.

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

api_instance = ClickSend::SmsCampaignsApi.new
sms_campaign_id = 'sms_campaign_id_example' # String | ID of SMS campaign to get
opts = {
  content_type: 'application/json' # String | 
}

begin
  # View Specific SMS Campaign
  result = api_instance.view_specific_sms_campaign(sms_campaign_id, opts)
  p result
rescue ClickSend::ApiError => e
  puts "Error when calling SmsCampaignsApi->view_specific_sms_campaign: #{e}"
end
```

#### Using the view_specific_sms_campaign_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ViewSpecificSmsCampaign>, Integer, Hash)> view_specific_sms_campaign_with_http_info(sms_campaign_id, opts)

```ruby
begin
  # View Specific SMS Campaign
  data, status_code, headers = api_instance.view_specific_sms_campaign_with_http_info(sms_campaign_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ViewSpecificSmsCampaign>
rescue ClickSend::ApiError => e
  puts "Error when calling SmsCampaignsApi->view_specific_sms_campaign_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **sms_campaign_id** | **String** | ID of SMS campaign to get |  |
| **content_type** | **String** |  | [optional] |

### Return type

[**ViewSpecificSmsCampaign**](ViewSpecificSmsCampaign.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

