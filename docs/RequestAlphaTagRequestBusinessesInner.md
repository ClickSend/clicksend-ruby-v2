# ClickSend::RequestAlphaTagRequestBusinessesInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **country** | **String** |  |  |
| **business_name** | **String** |  |  |
| **business_relationship** | **String** | Indicates your relationship to the business being registered.  - **PRIMARY**: Your primary business (linked to your ClickSend account). - **ENTITY_ASSOCIATE**: Sending on behalf of another business you represent or own.  |  |
| **business_info** | [**RequestAlphaTagRequestBusinessesInnerBusinessInfo**](RequestAlphaTagRequestBusinessesInnerBusinessInfo.md) |  |  |
| **business_address** | [**RequestAlphaTagRequestBusinessesInnerBusinessAddress**](RequestAlphaTagRequestBusinessesInnerBusinessAddress.md) |  |  |
| **representative** | [**RequestAlphaTagRequestBusinessesInnerRepresentative**](RequestAlphaTagRequestBusinessesInnerRepresentative.md) |  |  |
| **abn** | **String** | Australian Business Number (ABN), 11 digits |  |
| **partner_business_name** | **String** | Partner&#39;s business name. **Required** when &#x60;business_relationship&#x60; is &#x60;ENTITY_ASSOCIATE&#x60;. **Forbidden** otherwise.  | [optional] |
| **partner_abn** | **String** | Partner&#39;s Australian Business Number (ABN). Must contain only digits. **Required** when &#x60;business_relationship&#x60; is &#x60;ENTITY_ASSOCIATE&#x60;. **Forbidden** otherwise.  | [optional] |
| **partner_business_info** | [**RequestAlphaTagRequestBusinessesInnerBusinessInfo**](RequestAlphaTagRequestBusinessesInnerBusinessInfo.md) |  | [optional] |
| **partner_business_address** | [**RequestAlphaTagRequestBusinessesInnerBusinessAddress**](RequestAlphaTagRequestBusinessesInnerBusinessAddress.md) |  | [optional] |
| **partner_representative** | [**RequestAlphaTagRequestBusinessesInnerPartnerRepresentative**](RequestAlphaTagRequestBusinessesInnerPartnerRepresentative.md) |  | [optional] |

## Example

```ruby
require 'clicksend'

instance = ClickSend::RequestAlphaTagRequestBusinessesInner.new(
  country: null,
  business_name: null,
  business_relationship: null,
  business_info: null,
  business_address: null,
  representative: null,
  abn: null,
  partner_business_name: null,
  partner_abn: null,
  partner_business_info: null,
  partner_business_address: null,
  partner_representative: null
)
```

