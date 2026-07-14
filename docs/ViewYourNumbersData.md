# ClickSend::ViewYourNumbersData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total** | **Integer** | The total number of items available for viewing. | [optional] |
| **per_page** | **Integer** | The number of items returned per page. This is specified in the limit parameter. You can have 100 items at maximum, and 15 at minimum. | [optional] |
| **current_page** | **Integer** | The current page number. | [optional] |
| **last_page** | **Integer** | The last page number. | [optional] |
| **next_page_url** | **String** | A URL of the next page. It will return **null** if there’s no next page. | [optional] |
| **prev_page_url** | **String** | A URL of the previous page. It will return **null** if there’s no previous page. | [optional] |
| **from** | **Integer** | The number of the first result in the current page. | [optional] |
| **to** | **Integer** | The number of the last result in the current page. | [optional] |
| **data** | [**Array&lt;ViewYourNumbersDataAllOfDataInner&gt;**](ViewYourNumbersDataAllOfDataInner.md) |  | [optional] |
| **_currency** | [**Currency**](Currency.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewYourNumbersData.new(
  total: 2,
  per_page: 15,
  current_page: 1,
  last_page: 1,
  next_page_url: null,
  prev_page_url: null,
  from: 1,
  to: 2,
  data: [{&quot;dedicated_number&quot;:&quot;+61411111111&quot;,&quot;country&quot;:&quot;AU&quot;,&quot;price&quot;:&quot;18.59&quot;,&quot;_country_name&quot;:&quot;Australia&quot;,&quot;notes&quot;:null,&quot;type&quot;:&quot;sms&quot;,&quot;number_type&quot;:&quot;longcode&quot;,&quot;number_category&quot;:null,&quot;number_guid&quot;:&quot;60744953-781E-463C-A7FF-F194228674BB&quot;,&quot;form_submission_id&quot;:null,&quot;status&quot;:{&quot;value&quot;:0,&quot;label&quot;:&quot;REGISTRATION_NOT_REQUIRED&quot;,&quot;description&quot;:&quot;Your number is ready to go.&quot;,&quot;name&quot;:&quot;Ready to use&quot;}},{&quot;dedicated_number&quot;:&quot;+61422222222&quot;,&quot;country&quot;:&quot;AU&quot;,&quot;price&quot;:&quot;20.99&quot;,&quot;_country_name&quot;:&quot;Australia&quot;,&quot;notes&quot;:&quot;Business line&quot;,&quot;type&quot;:&quot;mms&quot;,&quot;number_type&quot;:&quot;longcode&quot;,&quot;number_category&quot;:null,&quot;number_guid&quot;:&quot;83955064-892F-574D-B8GG-G2053339785CC&quot;,&quot;form_submission_id&quot;:null,&quot;status&quot;:{&quot;value&quot;:1,&quot;label&quot;:&quot;REGISTRATION_NOT_INITIATED&quot;,&quot;description&quot;:&quot;Your number is unregistered. You will not be able to send messages to certain countries.&quot;,&quot;name&quot;:&quot;Unregistered&quot;}}],
  _currency: null
)
```

