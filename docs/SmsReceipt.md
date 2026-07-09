# ClickSend::SmsReceipt

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **timestamp_send** | **Integer** | The time you sent the test message. It’s in the &lt;a target&#x3D;\&quot;_blank\&quot; href&#x3D;\&quot;http://help.clicksend.com/what-is-a-unix-timestamp\&quot;&gt;Unix format&lt;/a&gt;. | [optional] |
| **timestamp** | **Integer** | The time you receive the test message receipt. It’s in the &lt;a target&#x3D;\&quot;_blank\&quot; href&#x3D;\&quot;http://help.clicksend.com/what-is-a-unix-timestamp\&quot;&gt;Unix format&lt;/a&gt;. | [optional] |
| **message_id** | **String** | The generated ID of the message. This ID is typically used as a reference for &lt;a target&#x3D;\&quot;_blank\&quot; href&#x3D;\&quot;https://www.clicksend.com/au/help/\&quot;&gt;customer support&lt;/a&gt; in case of any issues. | [optional] |
| **status_code** | **Integer** | The status code sent from the &lt;a target&#x3D;\&quot;_blank\&quot; href&#x3D;\&quot;https://en.wikipedia.org/wiki/SMS_gateway\&quot;&gt;SMS gateway&lt;/a&gt;. Visit &lt;a href&#x3D;\&quot;https://help.clicksend.com/article/8cc479qlbb-list-of-sms-gateway-error-codes\&quot;&gt;this page&lt;/a&gt; for more information. | [optional] |
| **status_text** | **String** | A message describing the status_code of the operation. Visit &lt;a href&#x3D;\&quot;https://help.clicksend.com/article/8cc479qlbb-list-of-sms-gateway-error-codes\&quot;&gt;this page&lt;/a&gt; for more information. | [optional] |
| **error_code** | **Integer** | The error code of the operation. Visit &lt;a href&#x3D;\&quot;https://help.clicksend.com/article/8cc479qlbb-list-of-sms-gateway-error-codes\&quot;&gt;this page&lt;/a&gt; for more information. If no error occurred, the value is **null**. | [optional] |
| **error_text** | **String** | A message describing the _error_code_ of the operation. Visit &lt;a href&#x3D;\&quot;https://help.clicksend.com/article/8cc479qlbb-list-of-sms-gateway-error-codes\&quot;&gt;this page&lt;/a&gt; for more information. If no error occurred, the value is **null**. | [optional] |
| **custom_string** | **String** | A note that was included with the outgoing SMS. If no note was included, the value is **null**. | [optional] |
| **subaccount_id** | **Integer** | The sub-account of the user. A user can have multiple sub-accounts. | [optional] |
| **message_type** | **String** | The type of message (e.g. SMS, MMS, etc). | [optional] |
| **digits** | **Integer** | The numbers that the recipient pressed on their keypad during the call. A **null** value is returned if the recipient didn&#39;t provide any input.  &lt;div class&#x3D;\&quot;info-box\&quot;&gt;   &lt;h4&gt;&lt;i class&#x3D;\&quot;fas fa-info-circle\&quot;&gt;&lt;/i&gt; Note:&lt;/h4&gt;   &lt;p&gt;This parameter is only relevant to &lt;a target&#x3D;\&quot;_blank\&quot; href&#x3D;\&quot;/messaging/voice-messaging/\&quot;&gt;&lt;strong&gt;Voice Messaging&lt;/strong&gt;&lt;/a&gt; receipts.&lt;/p&gt; &lt;/div&gt; | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::SmsReceipt.new(
  timestamp_send: 1442381791,
  timestamp: 1442381791,
  message_id: 31BC271B-1E0C-45F6-9E7E-97186C46BB82,
  status_code: 201,
  status_text: Success: Message received on handset.,
  error_code: null,
  error_text: null,
  custom_string: null,
  subaccount_id: null,
  message_type: sms,
  digits: null
)
```

