# ClickSend::Currency

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **currency_name_short** | **String** | The currency used for the sender in three-letter format (e.g. USD, EUR, AUD, NZD, etc). | [optional] |
| **currency_prefix_d** | **String** | The symbol used to indicate the currency of the sender (e.g. $ , €, etc). | [optional] |
| **currency_prefix_c** | **String** | The currency basic unit (e.g. cents). | [optional] |
| **currency_name_long** | **String** | The full name of the currency. | [optional] |
| **min_recharge_amount** | **String** | The minimum amount that can be used to recharge the account, in this currency. | [optional] |
| **max_recharge_amount** | **String** | The maximum amount that can be used to recharge the account, in this currency. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::Currency.new(
  currency_name_short: AUD,
  currency_prefix_d: $,
  currency_prefix_c: c,
  currency_name_long: Australian Dollars,
  min_recharge_amount: 20.00,
  max_recharge_amount: 10000.00
)
```

