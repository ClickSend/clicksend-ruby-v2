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
sms_message_collection = ClickSend::SmsMessageCollection.new(
  messages: [
    { source: 'sdk', body: 'Hello from ClickSend!', to: '+61411111111' }
  ]
)

begin
  result = api_instance.sms_send_post(sms_message_collection)
  p result
rescue ClickSend::ApiError => e
  puts "Exception when calling SmsApi->sms_send_post: #{e}"
end
```

## Authentication

The API uses HTTP Basic authentication — your ClickSend **username** and **API key** (available from the [ClickSend Dashboard](https://dashboard.clicksend.com/#/account/subaccount)).

## Documentation

Full API reference: https://developers.clicksend.com/docs/rest/v3/

## Support

Need help? Contact [ClickSend Support](https://clicksend.com/contact) or visit the [Help Centre](https://help.clicksend.com/).