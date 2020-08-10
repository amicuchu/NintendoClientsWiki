## [[SOAP Services]] > NetUpdateSOAP (NUS)

| Platform | Server |
| --- | --- |
| 3DS | https://nus.c.shop.nintendowifi.net/nus/services/NetUpdateSOAP |
| Wii U | https://nus.wup.shop.nintendo.net/nus/services/NetUpdateSOAP |

| Platform | User Agent |
| --- | --- |
| 3DS | `CTR NUP 040600 Mar 14 2012 13:32:39` |
| Wii U | `EVL NUP 040800 Sep 18 2012 20:20:02` |

## Method List
| Name |
| --- |
| GetSystemCommonETicket |
| [GetSystemTitleHash](#getsystemtitlehash) |
| [GetSystemUpdate](#getsystemupdate) |

## GetSystemTitleHash
Response tags:

| Tag | Description |
| --- | --- |
| `TitleHash` | 32 uppercase hex digits |

## GetSystemUpdate
The following tags are always returned:

| Tag | Description |
| --- | --- |
| `ContentPrefixURL` | 1. http://nus.cdn.shop.wii.com/ccs/download<br>3. http://nus.cdn.t.shop.nintendowifi.net/ccs/download<br>4. http://nus.cdn.c.shop.nintendowifi.net/ccs/download<br>5. http://nus.cdn.wup.shop.nintendo.net/ccs/download<br>7. http://nus.cdn.shop.wii.com/ccs/download |
| `UncachedContentPrefixURL` | 1. https://ccs.shop.wii.com/ccs/download<br>3. https://ccs.t.shop.nintendowifi.net/ccs/download<br>4. https://ccs.c.shop.nintendowifi.net/ccs/download<br>5. https://ccs.wup.shop.nintendo.net/ccs/download<br>7. https://ccs.shop.wii.com/ccs/download |
| `UploadAuditData` | Always 1 |
| `TitleHash` | Same as `GetSystemTitleHash` |

In addition, the server returns a list of `TitleVersion` tags, the content of which depends on the given device type:

| Tag | Device | Description |
| --- | --- | --- |
| `TitleId` | All | Title id (`%016X`) |
| `Version` | All | Title version (decimal integer) |
| `FsSize` | 1, 3, 4 | Filesystem size |
| `TicketSize` | 4, 5, 7 | Ticket size |
| `TMDSize` | 4, 5, 7 | TMD size |
| `RawSize` | 5, 7 | Raw size |