# ClickSend::CalculateEmailCampaignPriceDataData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** | Name. | [optional] |
| **subject** | **String** | Your template subject. | [optional] |
| **from_email_address_id** | **Float** | The allowed email address id. | [optional] |
| **from_name** | **String** | Your sender name. | [optional] |
| **body** | **String** | Your message. | [optional] |
| **list_id** | **Float** | Your list id. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CalculateEmailCampaignPriceDataData.new(
  name: John Doe,
  subject: Lorem Ipsum,
  from_email_address_id: 2,
  from_name: From name,
  body: &lt;p&gt;This is a test&lt;/p&gt;,
  list_id: 456
)
```

