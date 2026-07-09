# ClickSend::SmsCampaignSendersInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **recipient_country_code** | **String** | Recipient ISO country code | [optional] |
| **sender_id** | **String** | The sender ID you specified in the request. This parameter would not be returned if you did specify it in the SMS campaign. | [optional] |
| **sender_type** | **String** | The type of sender ID you specified in the request. This parameter would not be returned if you did specify it in the SMS campaign. | [optional] |
| **sender_country_code** | **String** | The country code of the sender you specified in the request. It is in two-letter format (e.g. US, UK, AU, NZ, &lt;a href&#x3D;\&quot;https://help.clicksend.com/article/7wtbhhy6sy-country-code-calling-code-list\&quot; target&#x3D;\&quot;_blank\&quot;&gt;etc&lt;/a&gt;).  For certain countries, you can receive SMS from abroad. This parameter would not be returned if you did specify it in the SMS campaign. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SmsCampaignSendersInner.new(
  recipient_country_code: null,
  sender_id: null,
  sender_type: null,
  sender_country_code: null
)
```

