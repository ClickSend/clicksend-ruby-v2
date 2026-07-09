# ClickSend::GetStatisticsDataInnerLinks

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total** | **Float** | Total number of recipients | [optional] |
| **opened_unique** | **Float** | Total number of recipients that clicked the short URL | [optional] |
| **opened_total** | **Float** | Total number of clicks on the short URL (e.g. when a recipient clicked the short URL twice, then it will add 2 here) | [optional] |
| **unopened** | **Float** | Total number of recipients that did not click the short URL (i.e. &#x60;total&#x60; - &#x60;opened_unique&#x60;) | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::GetStatisticsDataInnerLinks.new(
  total: 2,
  opened_unique: 2,
  opened_total: 5,
  unopened: 0
)
```

