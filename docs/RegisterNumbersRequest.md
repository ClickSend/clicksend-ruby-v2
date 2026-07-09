# ClickSend::RegisterNumbersRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **full_name** | **String** | Legal full name of the individual registering the number. Must be a personal name, not a business name. |  |
| **company_name** | **String** | Legal business name of the organization requesting registration |  |
| **email** | **String** | Contact email address for registration communications and notifications |  |
| **website_url** | **String** | Official business website URL |  |
| **sample_message** | **String** | Representative example of messages that will be sent using this number |  |
| **primary_use_case** | **String** | Primary intended purpose for the registered number (e.g., Marketing, Notifications, Authentication) |  |
| **company_number** | **String** | Official support phone number of the organization requesting registration |  |
| **area_code** | **String** | Your area codes, please provide your top 3 area codes in case your 1st choice is not available |  |

## Example

```ruby
require 'clicksend'

instance = ClickSend::RegisterNumbersRequest.new(
  full_name: John Doe,
  company_name: ClickSend,
  email: john.doe@clicksend.com,
  website_url: https://clicksend.com,
  sample_message: Get 20% off on your next purchase! Visit our website for details.,
  primary_use_case: Marketing,
  company_number: +1-800-555-0199,
  area_code: 416, 647, 905
)
```

