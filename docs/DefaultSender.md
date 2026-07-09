# ClickSend::DefaultSender

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | ID of the default sender. |  |
| **user_id** | **Integer** | User ID from the version 3 system. |  |
| **subaccount_id** | **Integer** | Subaccount ID from version 3. |  |
| **country_code** | **String** | ISO 3166-1 alpha-2 formatted country code. |  |
| **product_type** | **String** | Type of product for which the setting is applied. |  |
| **default_sender_strategies** | [**Array&lt;DefaultSenderDefaultSenderStrategiesInner&gt;**](DefaultSenderDefaultSenderStrategiesInner.md) | Default sender strategies. Must contain 1 or more objects. |  |
| **status** | **String** | Overall status of the default sender. |  |
| **created_timestamp** | **String** | Timestamp of when the default sender was created. Must be in ISO 8601 format. |  |
| **updated_timestamp** | **String** | Timestamp of the last update to the default sender. Must be in ISO 8601 format. |  |

## Example

```ruby
require 'clicksend'

instance = ClickSend::DefaultSender.new(
  id: f99872cc-11a6-48ba-a9f2-bcfb6dd1e3d4,
  user_id: 123456,
  subaccount_id: 45678,
  country_code: AU,
  product_type: SMS,
  default_sender_strategies: null,
  status: ENABLED,
  created_timestamp: 2021-08-02T00:00:00Z,
  updated_timestamp: 2021-08-02T00:00:00Z
)
```

