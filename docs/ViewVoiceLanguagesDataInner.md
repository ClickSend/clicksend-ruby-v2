# ClickSend::ViewVoiceLanguagesDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **code** | **String** | The code of the language. | [optional] |
| **country** | **String** | The country of the language. | [optional] |
| **gender** | **String** | The gender of the language. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewVoiceLanguagesDataInner.new(
  code: en-us,
  country: English, US,
  gender: male
)
```

