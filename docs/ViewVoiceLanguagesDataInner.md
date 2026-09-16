# ClickSend::ViewVoiceLanguagesDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **code** | **String** | The code of the language. | [optional] |
| **country** | **String** | The country of the language. | [optional] |
| **gender** | [**ViewVoiceLanguagesDataInnerGender**](ViewVoiceLanguagesDataInnerGender.md) |  | [optional] |

## Example

```ruby
require 'clicksend_client'

instance = ClickSend::ViewVoiceLanguagesDataInner.new(
  code: en-us,
  country: English, US,
  gender: null
)
```

