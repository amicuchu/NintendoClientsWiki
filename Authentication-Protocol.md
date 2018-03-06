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
| [Buffer] | [Kerberos ticket](Kerberos-Authentication#kerberos-ticket) |
| [RVConnectionData](NEX-Common-Types#rendez-vous-connection-data-structure) | Connection info for secure server |
| [String] | Server build name |

Examples of server build names:

| Server | Build name |
| --- | --- |
| Friends | branch:origin/feature/45925_FixAutoReconnect build:3_10_11_2006_0 |
| DKC:TF | branch:origin/release/ngs/3.4.x.3 build:3_4_8_3_0 |
| MK8 | branch:origin/project/wup-amk build:3_5_10_2010_0 |

# (2) LoginEx
## Request
| Type | Description |
| --- | --- |
| [String] | Username (user pid) |
| [Data]&lt;[AuthenticationInfo](#authentication-info)&gt; | Authentication info |

### Authentication Info
| Type | Description |
| --- | --- |
| [String] | Token, as received from the account server |
| Uint32 | Unknown, always 3? |
| Uint8 | Unknown, always 1? |
| Uint32 | Client version (see table below) |

| NEX Version | Client version |
| --- | --- |
| 3.4.0 | 3 |
| 3.5.4AMK (MK8) | 2002 |
| 3.8.10AMA (SMM) | 3017 |

## Response
Same as response for the [Login](#1-login) method.

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
| [Buffer] | [Kerberos ticket](Kerberos-Authentication#kerberos-ticket) |

# (4) GetPID
This is the reverse of the [GetName](#5-getname) method. It converts a given string to a PID that can be used in a station url.

## Request
| Type | Description |
| --- | --- |
| [String] | Name |

## Response
| Type | Description |
| --- | --- |
| Uint32 | PID |

# (5) GetName
This is the reverse of the [GetPID](#4-getpid) method. It returns the name of a given station url PID.

## Request
| Type | Description |
| --- | --- |
| Uint32 | PID |

## Response
| Type | Description |
| --- | --- |
| [String] | Name |

The following mapping seems to be used on all official servers:

| PID | Name |
| --- | --- |
| 1 | Quazal Authentication |
| 2 | Quazal Rendez-Vous |

# (6) LoginWithContext

[String]: NEX-Common-Types#string
[Buffer]: NEX-Common-Types#buffer
[Structure]: NEX-Common-Types#structure
[StationURL]: NEX-Common-Types#station-url
[List]: NEX-Common-Types#list
[DateTime]: NEX-Common-Types#date-time
[Data]: NEX-Common-Types#any-data-holder