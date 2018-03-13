[[NEX Protocols]] > Authentication (0x0A)
---
Alternative name: TicketGrantingProtocol

Each game server got two different servers: an authentication server and a secure server. This is the only protocol that runs on the authentication server. Other protocols are only available on the secure server.

| Method ID | Method Name |
| --- | --- |
| 1 | [Login](#1-login) |
| 2 | [LoginEx](#2-loginex) |
| 3 | [RequestTicket](#3-requestticket) |
| 4 | [GetPID](#4-getpid) |
| 5 | [GetName](#5-getname) |
| 6 | LoginWithContext |

# (1) Login
Alternative name: ValidateAndRequestTicket

## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strUserName | Username (user pid) |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | %retval% | Result code (also see [errors.py](https://github.com/Kinnay/NintendoClients/blob/master/nintendo/nex/errors.py)) |
| Uint32 | pidPrincipal |  User pid |
| [Buffer] | pbufResponse | [Kerberos ticket](Kerberos-Authentication#kerberos-ticket) |
| [RVConnectionData](NEX-Common-Types#rendez-vous-connection-data-structure) | pConnectionData | Connection info for secure server |
| [String] | strReturnMsg | Server build name |

Examples of server build names:

| Server | Build name |
| --- | --- |
| Friends | branch:origin/feature/45925_FixAutoReconnect build:3_10_11_2006_0 |
| DKC:TF | branch:origin/release/ngs/3.4.x.3 build:3_4_8_3_0 |
| MK8 | branch:origin/project/wup-amk build:3_5_10_2010_0 |

# (2) LoginEx
Alternative name: ValidateAndRequestTicketWithCustomData

## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strUserName | Username (user pid) |
| [Data]&lt;[AuthenticationInfo](#authentication-info)&gt; | oExtraData | Authentication info |

### Authentication Info
| Type | Name | Description |
| --- | --- | --- |
| [String] | m_authToken | Token, as received from the account server |
| Uint32 | m_ngsVersion | Always 3? |
| Uint8 | m_authTokenType | Always 1? |
| Uint32 | m_serverVersion | See table below |

| NEX Version | Server version |
| --- | --- |
| 3.4.0 | 3 |
| 3.5.4AMK (MK8) | 2002 |
| 3.8.10AMA (SMM) | 3017 |

## Response
Same as response for the [Login](#1-login) method.

# (3) RequestTicket
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idSource | User pid |
| Uint32 | idTarget | PID of secure server station url |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | %retval% | Result code |
| [Buffer] | bufResponse | [Kerberos ticket](Kerberos-Authentication#kerberos-ticket) |

# (4) GetPID
This is the reverse of the [GetName](#5-getname) method. It converts a given string to a PID that can be used in a station url.

## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strUserName | Name. "strUserName" is misleading, this is not actually a username |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | %retval% | PID |

# (5) GetName
This is the reverse of the [GetPID](#4-getpid) method. It returns the name of a given station url PID.

## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | id | PID |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [String] | %retval% | Name |

The following mapping seems to be used on all official servers:

| PID | Name |
| --- | --- |
| 1 | Quazal Authentication |
| 2 | Quazal Rendez-Vous |

[String]: NEX-Common-Types#string
[Buffer]: NEX-Common-Types#buffer
[Structure]: NEX-Common-Types#structure
[StationURL]: NEX-Common-Types#station-url
[List]: NEX-Common-Types#list
[DateTime]: NEX-Common-Types#date-time
[Data]: NEX-Common-Types#any-data-holder