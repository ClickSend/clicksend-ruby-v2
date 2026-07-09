# ClickSend::RequestOwnNumberVerificationOtp

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | The ID of the verification request. | [optional] |
| **own_number_id** | **String** | The ID of the own number. | [optional] |
| **status** | **String** | The status of the verification request. | [optional] |
| **expires_timestamp** | **String** | The expiration timestamp of the verification request. | [optional] |
| **remaining_attempts** | **Float** | The number of remaining attempts. | [optional] |
| **created_timestamp** | **String** | The creation timestamp of the verification request. | [optional] |
| **updated_timestamp** | **String** | The last update timestamp of the verification request. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::RequestOwnNumberVerificationOtp.new(
  id: db630385-cb76-457d-8f16-76df1b394257,
  own_number_id: db630385-cb76-457d-8f16-76df1b394257,
  status: APPROVED,
  expires_timestamp: 2023-08-31T12:00:00Z,
  remaining_attempts: 2,
  created_timestamp: 2023-08-25T08:00:00Z,
  updated_timestamp: 2023-08-25T08:10:00Z
)
```

