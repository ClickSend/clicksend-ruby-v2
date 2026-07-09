# ClickSend::InboundSmsTest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **timestamp_send** | **Integer** | The time you sent the test message. It’s in the &lt;a href&#x3D;\&quot;http://help.clicksend.com/what-is-a-unix-timestamp\&quot;&gt;Unix format.&lt;/a&gt; | [optional] |
| **from** | **String** | This is a random number used for testing purposes. | [optional] |
| **body** | **String** | The sample test message. | [optional] |
| **original_body** | **String** | The sample test message you sent to your recipient. | [optional] |
| **original_message_id** | **String** | The generated ID of the message that you sent to your receipient.  &lt;div class&#x3D;\&quot;info-box\&quot;&gt;   &lt;h4&gt;&lt;i class&#x3D;\&quot;fas fa-info-circle\&quot;&gt;&lt;/i&gt; Note:&lt;/h4&gt;   &lt;p&gt;This &lt;em&gt;original_message_id&lt;/em&gt; is different from the ID that is generated when sending an actual SMS. This ID is used for testing only.&lt;/p&gt; &lt;/div&gt; | [optional] |
| **to** | **String** | The receiver of the inbound message, which can be either the shared number or the dedicated number you used to send the message. | [optional] |
| **custom_string** | **String** | The sample test note that was included with the inbound SMS. | [optional] |
| **message_id** | **String** | The generated ID of the inbound SMS. This ID is typically used as a reference for &lt;a href&#x3D;\&quot;https://www.clicksend.com/au/help/\&quot; target&#x3D;\&quot;_blank\&quot;&gt;customer support&lt;/a&gt; in case of any issues. | [optional] |
| **_keyword** | **String** | The keyword of the inbound SMS.  &lt;div class&#x3D;\&quot;warning-box\&quot;&gt;   &lt;h4&gt;&lt;i class&#x3D;\&quot;fas fa-exclamation-triangle\&quot;&gt;&lt;/i&gt; Warning:&lt;/h4&gt;   &lt;p&gt;This parameter is deprecated and will return &lt;strong&gt;null.&lt;/strong&gt;&lt;/p&gt; &lt;/div&gt; | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::InboundSmsTest.new(
  timestamp_send: 1436174407,
  from: +61411111111,
  body: Liquorice sweet roll fruitcake gummies.,
  original_body: Liquorice sweet roll fruitcake gummies.,
  original_message_id: C557B56E-83C0-4070-A74C-9BF05474B418,
  to: +61422222222,
  custom_string: 22PKU978RF,
  message_id: C557B56E-83C0-4070-A74C-9BF05474B418,
  _keyword: liquorice
)
```

