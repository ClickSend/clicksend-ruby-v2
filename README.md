# ClickSend Ruby SDK

Official Ruby gem for the [ClickSend API](https://developers.clicksend.com/) — send and manage SMS, MMS, email, voice, fax, letters, postcards, and more.

## Installation

Add this to your Gemfile:

```ruby
gem 'clicksend', :git => 'https://github.com/ClickSend/clicksend-ruby-v2.git'
```

Then run:

```sh
bundle install
```

## Getting Started

```ruby
require 'clicksend'

ClickSend.configure do |config|
  config.username = ENV['CLICKSEND_USERNAME']
  config.password = ENV['CLICKSEND_API_KEY']
end

api_instance = ClickSend::SmsApi.new
send_sms_request = ClickSend::SendSmsRequest.new(
  messages: [
    { source: 'sdk', body: 'Hello from ClickSend!', to: '+61411111111' }
  ]
)

begin
  result = api_instance.send_sms(send_sms_request: send_sms_request)
  p result
rescue ClickSend::ApiError => e
  puts "Exception when calling SmsApi->send_sms: #{e}"
end
```

## More Examples

### View account details

```ruby
api_instance = ClickSend::ManagementApi.new

begin
  result = api_instance.view_account_details
  p result
rescue ClickSend::ApiError => e
  puts "Exception when calling ManagementApi->view_account_details: #{e}"
end
```

### Send an MMS

```ruby
api_instance = ClickSend::MmsApi.new
send_mms_request = ClickSend::SendMmsRequest.new(
  media_file: 'https://clicksend.com/logo.png',
  messages: [
    { source: 'sdk', to: '+61411111111', from: 'sdk', subject: 'Hello', body: 'Hello from ClickSend!' }
  ]
)

begin
  result = api_instance.send_mms(send_mms_request: send_mms_request)
  p result
rescue ClickSend::ApiError => e
  puts "Exception when calling MmsApi->send_mms: #{e}"
end
```

## Authentication

The API uses HTTP Basic authentication — your ClickSend **username** and **API key** (available from the [ClickSend Dashboard](https://dashboard.clicksend.com/#/account/subaccount)).

## Documentation

Full API reference: https://developers.clicksend.com/docs/rest/v3/

## Support

Need help? Contact [ClickSend Support](https://clicksend.com/contact) or visit the [Help Centre](https://help.clicksend.com/).