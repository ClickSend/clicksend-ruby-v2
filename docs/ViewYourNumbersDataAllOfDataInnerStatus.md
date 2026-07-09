# ClickSend::ViewYourNumbersDataAllOfDataInnerStatus

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **value** | **Integer** | Numeric status code (0-5): - 0: Your number is ready to go. - 1: Your number is unregistered. You will not be able to send messages to certain countries. - 2: Your number registration is in progress. Email updates will follow. - 3: Action required on your number registration. Please resolve to start using it. - 4: You can send to all countries but may get restricted to some before full registration. - 5: Your number is registered and you can start using it immediately.  | [optional] |
| **label** | **String** | Status label identifier corresponding to the numeric value above, following the same order. | [optional] |
| **description** | **String** | Human readable description of the status. | [optional] |
| **name** | **String** | Display name for the status corresponding to the numeric value above, following the same order. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewYourNumbersDataAllOfDataInnerStatus.new(
  value: 0,
  label: REGISTRATION_NOT_REQUIRED,
  description: Your number is ready to go.,
  name: Ready to use
)
```

