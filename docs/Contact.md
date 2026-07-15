# ClickSend::Contact

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **contact_id** | **Integer** | The unique identifier for the contact. | [optional] |
| **list_id** | **Integer** | The identifier of the list the contact belongs to. | [optional] |
| **phone_number** | **String** | The phone number of the contact. | [optional] |
| **first_name** | **String** | The first name of the contact. | [optional] |
| **last_name** | **String** | The last name of the contact. | [optional] |
| **custom_1** | **String** | Custom field 1. | [optional] |
| **custom_2** | **String** | Custom field 2. | [optional] |
| **custom_3** | **String** | Custom field 3. | [optional] |
| **custom_4** | **String** | Custom field 4. | [optional] |
| **date_added** | **Integer** | The date when the contact was added, as a &lt;a href&#x3D;\&quot;http://help.clicksend.com/what-is-a-unix-timestamp\&quot; target&#x3D;\&quot;_blank\&quot;&gt;Unix timestamp&lt;/a&gt;. | [optional] |
| **date_updated** | **Integer** | The date when the contact was last updated, as a &lt;a href&#x3D;\&quot;http://help.clicksend.com/what-is-a-unix-timestamp\&quot; target&#x3D;\&quot;_blank\&quot;&gt;Unix timestamp&lt;/a&gt;. | [optional] |
| **fax_number** | **String** | The fax number of the contact. | [optional] |
| **organization_name** | **String** | The organization name of the contact. | [optional] |
| **email** | **String** | The email address of the contact. | [optional] |
| **address_line_1** | **String** | The address line 1 of the contact. | [optional] |
| **address_line_2** | **String** | The address line 2 of the contact. | [optional] |
| **address_city** | **String** | The address city of the contact. | [optional] |
| **address_state** | **String** | The address state of the contact. | [optional] |
| **address_postal_code** | **String** | The address postal code of the contact. | [optional] |
| **address_country** | **String** | The address country of the contact. | [optional] |
| **_list_name** | **String** | The name of the list the contact belongs to. | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::Contact.new(
  contact_id: 552786,
  list_id: 428,
  phone_number: +16783270696,
  first_name: John,
  last_name: Doe,
  custom_1: Custom 1,
  custom_2: Custom 2,
  custom_3: Custom 3,
  custom_4: Custom 4,
  date_added: 1783997542,
  date_updated: 1783997542,
  fax_number: +61477141888,
  organization_name: Awesome Company,
  email: john@doe.com,
  address_line_1: 1554 Buffalo Creek Road,
  address_line_2: null,
  address_city: Nashville,
  address_state: TN,
  address_postal_code: 37214,
  address_country: US,
  _list_name: List6eaG4lGIc9
)
```

