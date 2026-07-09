# ClickSend::CreateTestSmsReceiptData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **timestamp_send** | **Integer** | The time you sent the test message. It is in &lt;a target&#x3D;\&quot;_blank\&quot; href&#x3D;\&quot;http://help.clicksend.com/what-is-a-unix-timestamp\&quot;&gt;Unix format.&lt;/a&gt; | [optional] |
| **timestamp** | **Integer** | The time you receive the test message receipt. It is in &lt;a target&#x3D;\&quot;_blank\&quot; href&#x3D;\&quot;http://help.clicksend.com/what-is-a-unix-timestamp\&quot;&gt;Unix format.&lt;/a&gt; | [optional] |
| **message_id** | **String** | The generated ID of the message. This ID is typically used as a reference for &lt;a target&#x3D;\&quot;_blank\&quot; href&#x3D;\&quot;https://www.clicksend.com/au/help/\&quot;&gt;customer support&lt;/a&gt; in case of any issues.  &lt;div class&#x3D;\&quot;info-box\&quot;&gt;   &lt;h4&gt;&lt;i class&#x3D;\&quot;fas fa-info-circle\&quot;&gt;&lt;/i&gt; Note:&lt;/h4&gt;   &lt;p&gt;This &lt;em&gt;message_id&lt;/em&gt; is different from the ID that is generated when sending or receving an actual SMS. This ID is used for testing only.&lt;/p&gt; &lt;/div&gt; | [optional] |
| **status_code** | **Integer** | The status code that is sent from the &lt;a target&#x3D;\&quot;_blank\&quot; href&#x3D;\&quot;https://en.wikipedia.org/wiki/SMS_gateway\&quot;&gt;SMS gateway.&lt;/a&gt; Visit &lt;a target&#x3D;\&quot;_blank\&quot; href&#x3D;\&quot;https://help.clicksend.com/article/8cc479qlbb-list-of-sms-gateway-error-codes\&quot;&gt;this page&lt;/a&gt; for more information. | [optional] |
| **status_text** | **String** | A message describing the _status_code_ of the operation. Visit &lt;a target&#x3D;\&quot;_blank\&quot; href&#x3D;\&quot;https://help.clicksend.com/article/8cc479qlbb-list-of-sms-gateway-error-codes\&quot;&gt;this&lt;/a&gt; page for more information. | [optional] |
| **error_code** | **Integer** | The error code of the operation. Visit &lt;a target&#x3D;\&quot;_blank\&quot; href&#x3D;\&quot;https://help.clicksend.com/article/8cc479qlbb-list-of-sms-gateway-error-codes\&quot;&gt;this page&lt;/a&gt; for more information. If no error occurred, the value is **null**. | [optional] |
| **error_text** | **String** | A message describing the _error_code_ of the operation. Visit &lt;a target&#x3D;\&quot;_blank\&quot; href&#x3D;\&quot;https://help.clicksend.com/article/8cc479qlbb-list-of-sms-gateway-error-codes\&quot;&gt;this page&lt;/a&gt; for more information. If no error occurred, the value is **null**. | [optional] |
| **custom_string** | **String** | A note that was sent from the request.  &lt;div class&#x3D;\&quot;warning-box\&quot;&gt;   &lt;h4&gt;&lt;i class&#x3D;\&quot;fas fa-exclamation-triangle\&quot;&gt;&lt;/i&gt; Warning:&lt;/h4&gt;   &lt;p&gt;This parameter is deprecated and will return &lt;strong&gt;null.&lt;/strong&gt;&lt;/p&gt; &lt;/div&gt; | [optional] |
| **subaccount_id** | **Integer** | The sub-account of the user. A user can have multiple sub-accounts. | [optional] |
| **message_type** | **String** | The type of message (e.g. SMS, MMS, etc). | [optional] |
| **digits** | **Integer** | The numbers that the recipient pressed on their keypad during the call. A **null** value is returned if the recipient didn&#39;t provide any input.  &lt;div class&#x3D;\&quot;info-box\&quot;&gt;   &lt;h4&gt;&lt;i class&#x3D;\&quot;fas fa-info-circle\&quot;&gt;&lt;/i&gt; Note:&lt;/h4&gt;   &lt;p&gt;This parameter is only relevant to &lt;a href&#x3D;\&quot;/messaging/voice-messaging/\&quot;&gt;&lt;strong&gt;Voice Messaging&lt;/strong&gt;&lt;/a&gt; receipts.&lt;/p&gt; &lt;/div&gt; | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::CreateTestSmsReceiptData.new(
  timestamp_send: 1722565411,
  timestamp: 1722565411,
  message_id: 2336751A-BBBE-4887-9D7C-CB7558F00208,
  status_code: 201,
  status_text: Success: Message received on handset.,
  error_code: null,
  error_text: null,
  custom_string: null,
  subaccount_id: 563840,
  message_type: sms,
  digits: null
)
```

