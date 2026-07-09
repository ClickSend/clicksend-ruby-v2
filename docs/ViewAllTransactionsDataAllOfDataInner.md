# ClickSend::ViewAllTransactionsDataAllOfDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **invoice_number** | **String** | The invoice number. | [optional] |
| **amount** | **Float** | The amount of the transaction. | [optional] |
| **currency** | **String** | The currency of the transaction. | [optional] |
| **date** | **Float** | The date of the transaction. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::ViewAllTransactionsDataAllOfDataInner.new(
  invoice_number: cb726c65-1c65-47fa-aea2-3ded9ed57557,
  amount: 20,
  currency: AUD,
  date: 1443420196
)
```

