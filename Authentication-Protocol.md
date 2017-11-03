[[NEX Protocols]] > Authentication (0x0A)
---

Each game server got two different servers: an authentication server and a secure server. This is the only protocol that runs on the authentication server. Other protocols are only available on the secure server.

| Method ID | Method Name |
| --- | --- |
| 1 | [Login](#1-login) |
| 2 | [LoginEx](#2-loginex) |
| 3 | [RequestTicket](#3-requestticket) |
| 4 | [GetPID](#4-getpid) |
| 5 | [GetName](#5-getname) |
| 6 | [LoginWithContext](#6-loginwithcontext) |

# (1) Login
## Request
| Type | Description |
| --- | --- |
| [String] | Username (user pid) |

## Response
| Type | Description |
| --- | --- |
| Uint32 | Result code (also see [errors.py](https://github.com/Kinnay/NintendoClients/blob/master/nintendo/nex/errors.py)) |
| Uint32 | User pid |
| [Buffer] | [Kerberos ticket](#kerberos-ticket) |
| [ConnectionData](#connection-data-structure) | Connection info for secure server |
| [String] | Server build name |

Examples of server build names:

| Server | Build name |
| --- | --- |
| Friends | branch:origin/feature/45925_FixAutoReconnect build:3_10_11_2006_0 |
| DKC:TF | branch:origin/release/ngs/3.4.x.3 build:3_4_8_3_0 |
| MK8 | branch:origin/project/wup-amk build:3_5_10_2010_0 |

### Connection Data ([Structure])
| Type | Version | Description |
| --- | --- | --- |
| [StationURL] | Any | Secure server address |
| [List]&lt;byte&gt; | Any | Unknown, official servers send an empty list |
| [StationURL] | Any | Unknown, official servers send an empty url, that is, just "prudp:/" |
| [DateTime] | V1 | Server time |

Examples:

| Server | Station url |
| --- | --- |
| Friends | `prudps:/stream=10;type=2;PID=2;port=60091;address=35.162.205.114;sid=1;CID=1` |
| DKC:TF | `prudps:/port=43221;CID=1;address=34.208.166.202;PID=2;stream=10;type=2;sid=1` |
| MK8 | `prudps:/sid=1;port=59201;address=52.10.188.163;PID=2;stream=10;type=2;CID=1` |

# (2) LoginEx

# (3) RequestTicket
## Request
| Type | Description |
| --- | --- |
| Uint32 | User pid |
| Uint32 | PID of secure server station url |

## Response
| Type | Description |
| --- | --- |
| Uint32 | Result code |
| [Buffer] | [Kerberos ticket](#kerberos-ticket) |

### Kerberos Ticket
TODO

# (4) GetPID

# (5) GetName

# (6) LoginWithContext

[String]: NEX-Common-Types#string
[Buffer]: NEX-Common-Types#buffer
[Structure]: NEX-Common-Types#structure
[StationURL]: NEX-Common-Types#station-url
[List]: NEX-Common-Types#list
[DateTime]: NEX-Common-Types#date-time