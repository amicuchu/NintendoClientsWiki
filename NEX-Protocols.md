As stated on the [[Game Server Overview]] page, NEX is actually a Nintendo-version of Quazal. As a consequence, both libraries share the same services, but NEX only provides a handful of them.

## Common Protocols
| ID | NEX | Protocol |
| --- | --- | --- |
| 0x01 | Yes | [Remote log device](Remote-Log-Device-Protocol) |
| 0x03 | Yes | [NAT traversal](NAT-Traversal-Protocol) |
| 0x0A | Yes | [Authentication](Authentication-Protocol) |
| 0x0B | Yes | [Secure connection](Secure-Protocol) |
| 0x0E | Yes | [Notification events](Notification-Protocol) |
| 0x10 | No | Simple authentication |
| 0x11 | No | Siege |
| 0x12 | Yes | [Health](Health-Protocol) |
| 0x13 | Yes | [Monitoring](Monitoring-Protocol) |
| 0x14 | No | Friends |
| 0x15 | Yes | [Match making](Match-Making-Protocol) |
| 0x17 | Yes | [Messaging](Messaging-Protocol) |
| 0x18 | No | Persistent store |
| 0x19 | Yes | [Account management](Account-Management-Protocol) |
| 0x1B | Yes | [Message delivery](Message-Delivery-Protocol) |
| 0x1C | No | Client settings |
| 0x1D | No | Ubi account management |
| 0x1E | No | Geo localization |
| 0x1F | No | News |
| 0x23 | No | Privileges |
| 0x24 | No | Tracking / telemetry |
| 0x27 | No | Localization |
| 0x2A | No | Game session |
| 0x2C | No | Sub account management |
| 0x2D | No | IP to location |
| 0x2E | No | IP to location admin |
| 0x2F | No | Ubi friends |
| 0x30 | No | Skill rating |
| 0x31 | No | Uplay win |
| 0x32 | Yes | [Match making (extension)](Match-Making-Protocol-Ext) |
| 0x33 | No | Title storage |
| 0x35 | No | User storage |
| 0x37 | No | Player stats |
| 0x47 | No | Offline game notifications |
| 0x48 | No | User account management |
| 0x54 | No | Siege admin |

## Nintendo Only

| 0x64 | [Nintendo notification events](Nintendo-Notification-Event-Protocol) |
| 0x65 | Friends-related? |
| 0x66 | [Friends](Friends-Protocol) |
| 0x6D | [Matchmake extension](Matchmake-Extension-Protocol) |
| 0x6E | [Utility](Utility-Protocol) |
| 0x70 | [Ranking](Ranking-Protocol) |
| 0x73 | [Data store](Data-Store-Protocol) |
| 0x7A | [Ranking 2](Ranking-Protocol-2) |