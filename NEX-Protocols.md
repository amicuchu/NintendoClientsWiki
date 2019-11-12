As stated on the [Game Server Overview](NEX-Overview-(Game-Servers)) page, NEX is actually a Nintendo-version of Quazal Rendez-Vous. As a consequence, both libraries share the same services, but NEX only provides a handful of them.

See also: [[RMC Protocol]]

## Common Protocols
| ID | Protocol |
| --- | --- |
| 0x01 | [Remote log device](Remote-Log-Device-Protocol) |
| 0x03 | [NAT traversal](NAT-Traversal-Protocol) |
| 0x0A | [Authentication](Authentication-Protocol) |
| 0x0B | [Secure connection](Secure-Protocol) |
| 0x0E | [Notification events](Notification-Protocol) |
| 0x12 | [Health](Health-Protocol) |
| 0x13 | [Monitoring](Monitoring-Protocol) |
| 0x14 | [Friends](Friends-Protocol) |
| 0x15 | [Match making](Match-Making-Protocol) |
| 0x17 | [Messaging](Messaging-Protocol) |
| 0x18 | [Persistent store](Persistent-Store-Protocol) |
| 0x19 | [Account management](Account-Management-Protocol) |
| 0x1B | [Message delivery](Message-Delivery-Protocol) |
| 0x32 | [Match making (extension)](Match-Making-Protocol-Ext) |

## Nintendo Only

| ID | Protocol |
| --- | --- |
| 0x64 | [Nintendo notification events](Nintendo-Notification-Event-Protocol) |
| 0x65 | [Friends (3DS)](Friends-Protocol-(3DS)) |
| 0x66 | [Friends (Wii U)](Friends-Protocol-(Wii-U)) |
| 0x6D | [Matchmake extension](Matchmake-Extension-Protocol) |
| 0x6E | [Utility](Utility-Protocol) |
| 0x70 | [Ranking](Ranking-Protocol) |
| 0x73 | [Data store](Data-Store-Protocol) |
| 0x74 | [Debug](Debug-Protocol) |
| 0x78 | ? |
| 0x79 | Subscriber |
| 0x7A | [Ranking 2](Ranking-Protocol-2) |
| 0x7B | ? |
| 0x7C | Screening |

## Not provided by Nintendo
| ID | Protocol |
| --- | --- |
| 0x0C | Back end management |
| 0x10 | [Simple authentication](Simple-Authentication-Protocol) |
| 0x11 | Siege |
| 0x1C | Client settings |
| 0x1D | Ubi account management |
| 0x1E | Geo localization |
| 0x1F | News |
| 0x23 | Privileges |
| 0x24 | Tracking / telemetry |
| 0x27 | Localization |
| 0x2A | Game session |
| 0x2C | Sub account management |
| 0x2D | IP to location |
| 0x2E | IP to location admin |
| 0x2F | Ubi friends |
| 0x30 | Skill rating |
| 0x31 | Uplay win |
| 0x33 | Title storage |
| 0x35 | User storage |
| 0x37 | Player stats |
| 0x47 | Offline game notifications |
| 0x48 | User account management |
| 0x54 | Siege admin |