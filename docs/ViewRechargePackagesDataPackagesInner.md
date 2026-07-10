# ClickSend::ViewRechargePackagesDataPackagesInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **package_id** | **Float** | The ID of the package. | [optional] |
| **package_price** | **String** | The price of the package. | [optional] |
| **price_rate** | **Integer** | The pricing tier used to determine the cost per message. | [optional] |
| **sms_price** | **Float** | The price of the SMS. | [optional] |
| **sms_quantity** | **Float** | The quantity of the SMS. | [optional] |
| **voice_mobile_price** | **Float** | The price of the voice mobile. | [optional] |
| **voice_mobile_quantity** | **Float** | The quantity of the voice mobile. | [optional] |
| **voice_landline_price** | **Float** | The price of the voice landline. | [optional] |
| **voice_landline_quantity** | **Float** | The quantity of the voice landline. | [optional] |
| **fax_price** | **Float** | The price of the fax. | [optional] |
| **fax_quantity** | **Float** | The quantity of the fax. | [optional] |
| **email_price** | **Float** | The price of the email. | [optional] |
| **email_quantity** | **Float** | The quantity of the email. | [optional] |
| **post_letter_black_price** | **Float** | The price of the post letter black. | [optional] |
| **post_letter_colour_price** | **Float** | The price of the post letter colour. | [optional] |
| **post_page_black_price** | **Float** | The price of the post page black. | [optional] |
| **post_page_colour_price** | **Float** | The price of the post page colour. | [optional] |
| **post_letter_black_quantity** | **Float** | The quantity of the post letter black. | [optional] |
| **post_letter_colour_quantity** | **Float** | The quantity of the post letter colour. | [optional] |
| **post_direct_mail_dl_price** | **Float** | The price of the post direct mail dl. | [optional] |
| **post_direct_mail_a5_price** | **Float** | The price of the post direct mail a5. | [optional] |
| **post_direct_mail_min_quantity** | **Float** | The quantity of the post direct mail min. | [optional] |
| **postcard_price** | **Float** | The price of the postcard. | [optional] |
| **postcard_quantity** | **Float** | The quantity of the postcard. | [optional] |
| **automation_price** | **Float** | The price of the automation. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewRechargePackagesDataPackagesInner.new(
  package_id: 1,
  package_price: 20,
  price_rate: 0,
  sms_price: 0.099,
  sms_quantity: 202,
  voice_mobile_price: 0.99,
  voice_mobile_quantity: 202,
  voice_landline_price: 0.0583,
  voice_landline_quantity: 343,
  fax_price: 0.198,
  fax_quantity: 101,
  email_price: 0.033,
  email_quantity: 606,
  post_letter_black_price: 1.397,
  post_letter_colour_price: 1.617,
  post_page_black_price: 0.11,
  post_page_colour_price: 0.264,
  post_letter_black_quantity: 13,
  post_letter_colour_quantity: 10,
  post_direct_mail_dl_price: 0.44,
  post_direct_mail_a5_price: 0.44,
  post_direct_mail_min_quantity: 5000,
  postcard_price: 11,
  postcard_quantity: 1,
  automation_price: 0.0017
)
```

