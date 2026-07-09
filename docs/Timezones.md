# ClickSend::Timezones

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **http_code** | **Integer** | The HTTP status code of the response. | [optional] |
| **response_code** | **String** | The response code indicating the status of the operation. | [optional] |
| **response_msg** | **String** | A message describing the outcome of the operation. | [optional] |
| **data** | **Array&lt;String&gt;** |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::Timezones.new(
  http_code: 200,
  response_code: SUCCESS,
  response_msg: List of timezones.,
  data: [&quot;Africa/Abidjan&quot;,&quot;Africa/Accra&quot;,&quot;Africa/Addis_Ababa&quot;,&quot;Africa/Algiers&quot;,&quot;Africa/Asmara&quot;,&quot;Africa/Asmera&quot;,&quot;Africa/Bamako&quot;,&quot;Africa/Bangui&quot;,&quot;Africa/Banjul&quot;,&quot;Africa/Bissau&quot;,&quot;Africa/Blantyre&quot;,&quot;Africa/Brazzaville&quot;,&quot;Africa/Bujumbura&quot;,&quot;Africa/Cairo&quot;,&quot;Africa/Casablanca&quot;,&quot;Africa/Ceuta&quot;,&quot;Africa/Conakry&quot;,&quot;Africa/Dakar&quot;,&quot;Africa/Dar_es_Salaam&quot;,&quot;Africa/Djibouti&quot;,&quot;etc...&quot;]
)
```

