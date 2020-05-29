## [[SOAP Services]] > NetUpdateSOAP (NUS)

This server is at https://nus.wup.shop.nintendo.net/nus/services/NetUpdateSOAP.

The user agent is: `EVL NUP 040800 Sep 18 2012 20:20:02`.

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
| `nus:DeviceId` | <code>MCP_GetDeviceId() &vert; (5 << 32)</code> |
| `nus:RegionId` | Region id (e.g. `EUR`) |
| `nus:CountryCode` | Country code (e.g. `NL`) |