# ClickSend::Sms

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **date** | **String** | The date you sent the message. It is in &lt;a href&#x3D;\&quot;http://help.clicksend.com/what-is-a-unix-timestamp\&quot; target&#x3D;\&quot;_blank\&quot;&gt;Unix format&lt;/a&gt;. Returned as a string since it may be an empty string in price-calculation responses where no message has actually been sent yet. | [optional] |
| **to** | **String** | The phone number of the recipient. It should be in &lt;a href&#x3D;\&quot;https://en.wikipedia.org/wiki/E.164\&quot; target&#x3D;\&quot;_blank\&quot;&gt;E.164 format&lt;/a&gt;. | [optional] |
| **body** | **String** | The message sent. The price of sending a message depends on the number of characters and the type of message. There are two types:  - Standard message - Contains only characters in the &lt;a href&#x3D;\&quot;https://en.wikipedia.org/wiki/GSM_03.38\&quot; target&#x3D;\&quot;_blank\&quot;&gt;GSM&lt;/a&gt; set, with a maximum of 160 characters.      - Unicode message - Contains characters outside the &lt;a href&#x3D;\&quot;https://en.wikipedia.org/wiki/GSM_03.38\&quot; target&#x3D;\&quot;_blank\&quot;&gt;GSM&lt;/a&gt; set, with a maximum of 70 characters.       Longer messages will be sent as multiple messages (parts), but the recipient will receive them as a single long message. Visit &lt;a href&#x3D;\&quot;https://help.clicksend.com/article/h474eseq3a-how-many-characters-can-i-send-in-an-sms\&quot; target&#x3D;\&quot;_blank\&quot;&gt;this page&lt;/a&gt; to learn more about the number of characters per message, and &lt;a href&#x3D;\&quot;http://smscharactercount.com/\&quot; target&#x3D;\&quot;_blank\&quot;&gt;this page&lt;/a&gt; to count the number of characters. | [optional] |
| **from** | **String** | The sender of the message. This is also referred to as the **Sender ID**. If your **Sender ID** has a different country code to the recipient’s, it&#39;ll be replaced by a local number, except in &lt;a href&#x3D;\&quot;https://help.clicksend.com/category/mfdctha7f0-country-specific-features-and-restrictions\&quot; target&#x3D;\&quot;_blank\&quot;&gt;certain countries&lt;/a&gt;. If the sender number is blocked, a different number will replace it. | [optional] |
| **schedule** | **String** | The scheduled date of the message. It is in &lt;a href&#x3D;\&quot;http://help.clicksend.com/what-is-a-unix-timestamp\&quot; target&#x3D;\&quot;_blank\&quot;&gt;Unix format&lt;/a&gt;. | [optional] |
| **message_id** | **String** | The generated ID of the message. This ID is typically used as a reference for &lt;a href&#x3D;\&quot;https://www.clicksend.com/au/help/\&quot; target&#x3D;\&quot;_blank\&quot;&gt;customer support&lt;/a&gt; in case of any issues. | [optional] |
| **message_parts** | **Integer** | The number of parts the message was broken into. To look at how many parts your message is broken down into, use the **&lt;a href&#x3D;\&quot;http://smscharactercount.com/\&quot;&gt;SMS Character Count&lt;/a&gt;**. | [optional] |
| **message_price** | **String** | The price of this message. This depends on the total number of parts of the message. | [optional] |
| **custom_string** | **String** | A note that was sent from the request. | [optional] |
| **contact_id** | **String** | This is the ID of the contact. This parameter will have a **null** value if you didn’t provide a _contact_id_ in the request. | [optional] |
| **is_shared_system_number** | **Boolean** | Indicates whether you use a shared number to send a message:  - **True** \\- if the sender is randomly selected.      - **False** \\- if the sender is specified and passed the validation process. | [optional] |
| **country** | **String** | The country of the recipient in two-letter format (e.g. US, UK, AU, NZ, etc). | [optional] |
| **status** | **String** | The response code of the operation. Visit [this page](/#application-status-codes) for more information. This reflects the actual status of the individual message. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::Sms.new(
  date: 1436871253,
  to: +61411111111,
  body: Jelly liquorice marshmallow candy carrot cake 4Eyffjs1vL.,
  from: sendmobile,
  schedule: 1436874701,
  message_id: BF7AD270-0DE2-418B-B606-71D527D9C1AE,
  message_parts: 1,
  message_price: 0.07,
  custom_string: this is a test,
  contact_id: 52649412,
  is_shared_system_number: false,
  country: AU,
  status: SUCCESS
)
```

