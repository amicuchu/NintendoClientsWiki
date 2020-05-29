## [[SOAP Services]] > NetUpdateSOAP (NUS)

| Platform | Server |
| --- | --- |
| 3DS | https://nus.c.shop.nintendowifi.net/nus/services/NetUpdateSOAP |
| Wii U | https://nus.wup.shop.nintendo.net/nus/services/NetUpdateSOAP |

| Platform | User agent |
| --- | --- |
| 3DS | `CTR NUP 040600 Mar 14 2012 13:32:39` |
| Wii U | `EVL NUP 040800 Sep 18 2012 20:20:02` |

## Method List
| Name |
| --- |
| GetSystemCommonETicket |
| GetSystemTitleHash |
| GetSystemUpdate |

## Additional Parameters
In addition to `Version` and `MessageId`, the following parameters are always present:

| Parameter | Description |
| --- | --- |
| `nus:DeviceId` | See description of device id on the page about [SOAP services](SOAP-Services) |
| `nus:RegionId` | Region id (e.g. `EUR`) |
| `nus:CountryCode` | Country code (e.g. `NL`) |