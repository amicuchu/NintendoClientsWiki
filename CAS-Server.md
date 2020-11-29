## [SOAP Services](SOAP-Services.md) > CatalogingSOAP (CAS)

| Platform | Server |
| --- | --- |
| 3DS | https://cas.c.shop.nintendowifi.net/cas/services/CatalogingSOAP |
| Wii U | https://cas.wup.shop.nintendo.net/cas/services/CatalogingSOAP |

| Platform | User Agent |
| --- | --- |
| 3DS | `CTR EC 040600 Mar 14 2012 13:32:39` |
| Wii U | `EVL EC 040800 Sep 18 2012 20:20:02` |

## Method List
| Name |
| --- |
| GetContentSizes |
| GetCountryMigrateAttributes |
| GetMessages |
| ListCashReplenishAmounts |
| ListContentSetGroups |
| ListContentSets |
| ListContentSetsEx |
| ListECardItemPricings |
| ListECardItems |
| ListItems |
| ListPointsPricings |
| ListTitles |
| ListTitlesEx |

## Errors
| Code | Message |
| --- | --- |
| 2 | Database connection error.: SQL Exception |
| 1702 | Invalid title ID<br>Invalid title ID: Error parsing title `...` |
| 1703 | Application Id is required: Missing applicationId |
| 1704 | Invalid application ID: Invalid applicationId `...` |
| 1706 | Invalid country code |
| 1710 | AppId/TIN validation failed: Either applicationId (`...`) or TIN (`...`) are wrong. |
| 1711 | TIN is required: Missing TIN |
| 1712 | Invalid TIN: Error parsing TIN `...` |
| 1719 | No messages found |
| 1720 | Declared array contains null value or is null: Values array in Attribute Filters is null. |
| 1722 | Device id is required. |
| 1735 | Invalid ecard type: ECardIdentifier is not specified |
| 1736 | Invalid Parameter: Invalid Parameter - ListResultLimit cannot be negative<br>Invalid Parameter: Invalid Parameter - ListResultOffset cannot be negative |
| 1791 | CAS cache error<br>CAS cache error: key must be of type String or Integer |
| 1799 | CAS internal error: Unexpected error: null |