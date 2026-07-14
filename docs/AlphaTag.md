# ClickSend::AlphaTag

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | The unique identifier for the record. | [optional] |
| **account_id** | **String** | The unique identifier for the account. | [optional] |
| **workspace_id** | **String** | The unique identifier for the workspace. | [optional] |
| **user_id** | **String** | The unique identifier for the user. | [optional] |
| **alpha_tag** | **String** | The alpha tag. | [optional] |
| **status** | **String** | The status of the record. | [optional] |
| **reason** | **String** | The reason for the status. | [optional] |
| **countries** | **Array&lt;String&gt;** | List of country codes where the alpha tag is requested. If not provided, it means a global alpha tag. | [optional] |
| **created_timestamp** | **String** | The timestamp when the record was created. Usually ISO 8601 (e.g. \&quot;2021-05-11T01:00:00.123Z\&quot;), but returned as a plain string rather than a strict date-time since some older records don&#39;t include a UTC offset (e.g. \&quot;2024-01-10T10:55:26.818097\&quot;). | [optional] |
| **updated_timestamp** | **String** | The timestamp when the record was last updated. Usually ISO 8601 (e.g. \&quot;2021-05-11T01:05:00.123Z\&quot;), but returned as a plain string rather than a strict date-time since some older records don&#39;t include a UTC offset. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::AlphaTag.new(
  id: db630385-cb76-457d-8f16-76df1b394257,
  account_id: 85edb794-ee6d-4a38-9f63-c5fa8acf0d79,
  workspace_id: 85edb794-ee6d-4a38-9f63-c5fa8acf0d79,
  user_id: 85edb794-ee6d-4a38-9f63-c5fa8acf0d79,
  alpha_tag: Abc123,
  status: PENDING,
  reason: Sole Trader Name,
  countries: [&quot;AU&quot;],
  created_timestamp: 2021-05-11T01:00:00.123Z,
  updated_timestamp: 2021-05-11T01:05:00.123Z
)
```

