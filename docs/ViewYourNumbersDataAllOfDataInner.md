# ClickSend::ViewYourNumbersDataAllOfDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **dedicated_number** | **String** | The dedicated number. | [optional] |
| **country** | **String** | The country. | [optional] |
| **price** | **String** | The price. | [optional] |
| **_country_name** | **String** | The country name. | [optional] |
| **notes** | **String** | Optional notes about the number. | [optional] |
| **type** | **String** | The type of messages this number can send. | [optional] |
| **number_type** | **String** | The classification of the number. | [optional] |
| **number_category** | **String** | The category of the number. | [optional] |
| **number_guid** | **String** | Unique identifier for the number. | [optional] |
| **form_submission_id** | **String** | ID of any associated form submission. | [optional] |
| **status** | [**ViewYourNumbersDataAllOfDataInnerStatus**](ViewYourNumbersDataAllOfDataInnerStatus.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewYourNumbersDataAllOfDataInner.new(
  dedicated_number: +61411111111,
  country: AU,
  price: 18.59,
  _country_name: Australia,
  notes: Business line,
  type: sms,
  number_type: longcode,
  number_category: null,
  number_guid: 60744953-781E-463C-A7FF-F194228674BB,
  form_submission_id: null,
  status: null
)
```

