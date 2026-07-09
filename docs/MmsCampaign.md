# ClickSend::MmsCampaign

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **mms_campaign_id** | **Integer** | The ID of the MMS campaign. | [optional] |
| **name** | **String** | The name of the MMS campaign. | [optional] |
| **user_id** | **Integer** | The ID of the user who created the campaign. | [optional] |
| **subaccount_id** | **Integer** | The ID of the subaccount associated with the campaign. | [optional] |
| **list_id** | **Integer** | The ID of the list associated with the campaign. | [optional] |
| **from** | **String** | The sender&#39;s phone number or ID. | [optional] |
| **subject** | **String** | The subject of the MMS campaign. | [optional] |
| **file_name** | **String** | The name of the media file attached to the MMS. | [optional] |
| **body** | **String** | The body or content of the MMS. | [optional] |
| **schedule** | **Integer** | The schedule time of the MMS campaign. | [optional] |
| **status** | **String** | The status of the MMS campaign. | [optional] |
| **date_added** | **Integer** | The date when the campaign was added. | [optional] |
| **_total_count** | **Integer** | The total count associated with the campaign. | [optional] |
| **_list_name** | **String** | The name of the list associated with the campaign. | [optional] |
| **_media_file_url** | **String** | The URL of the media file attached to the MMS. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::MmsCampaign.new(
  mms_campaign_id: 96,
  name: Koala Campaign,
  user_id: 20807,
  subaccount_id: 15,
  list_id: 85262,
  from: 0451919865,
  subject: New MMS campaign test,
  file_name: 8EA5FA8C-3216-4A5D-86EA-6BE78050E439.jpg,
  body: Hey (First Name), I want to ask if this is your lastname: (Last Name)? Also, do you like koalas? Visit http://smsu.io/xxxxx for more details.,
  schedule: 1531800743,
  status: Queued,
  date_added: 1531800745,
  _total_count: 1,
  _list_name: test,
  _media_file_url: http://rest.clicksend.clicksend/files/8EA5FA8C-3216-4A5D-86EA-6BE78050E439.jpg
)
```

