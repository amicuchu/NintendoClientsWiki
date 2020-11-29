[NEX Protocols](NEX-Protocols.md) > Authentication (0x0A)
---
Official name: TicketGrantingProtocol

This is the only protocol that's available on the authentication server. Other protocols are only available on the secure server.

| Method ID | Name (Wii U) | Name (Switch) |
| --- | --- | --- |
| 1 | [Login](#1-login) | [ValidateAndRequestTicket](#1-login) |
| 2 | [LoginEx](#2-loginex) | [ValidateAndRequestTicketWithCustomData](#2-loginex) |
| 3 | [RequestTicket](#3-requestticket) | [RequestTicket](#3-requestticket) |
| 4 | [GetPID](#4-getpid) | [GetPID](#4-getpid) |
| 5 | [GetName](#5-getname) | [GetName](#5-getname) |
| 6 | [LoginWithContext](#6-loginwithcontext) | [ValidateAndRequestTicketWithParam](#6-validateandrequestticketwithparam) |

# (1) Login
Alternative name: ValidateAndRequestTicket

## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strUserName | Username |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [Result] | %retval% | Result code |
| [PID] | pidPrincipal |  User pid |
| [Buffer] | pbufResponse | [Kerberos ticket](Kerberos-Authentication.md#kerberos-ticket) |
| [RVConnectionData] | pConnectionData | Connection info for secure server.<br><br>The Nintendo Switch allows the secure server to be at the same address as the authentication server. In that case, the secure server station url points to  0.0.0.1 with port 1. |
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
| [String] | strUserName | Username |
| [Any]&lt;[AuthenticationInfo](#authenticationinfo-structure)&gt; | oExtraData | Authentication info |

### AuthenticationInfo ([Structure])
| This structure inherits from [Data] |
| --- |

| Type | Name | Description |
| --- | --- | --- |
| [String] | m_authToken | Token, as received from the account server |
| Uint32 | m_ngsVersion | Always 3 on Wii U. Always 4 on Switch. |
| Uint8 | m_authTokenType | Always 1 on Wii U. Always 2 on Switch. |
| Uint32 | m_serverVersion | See table below |

| NEX Version | Server version |
| --- | --- |
| 3.4.0 | 3 |
| 3.5.4AMK (MK8) | 2002 |
| 3.8.10AMA (SMM) | 3017 |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [Result] | %retval% | Result code |
| [PID] | pidPrincipal | User pid |
| [Buffer] | pbufResponse | [Kerberos ticket](Kerberos-Authentication.md#kerberos-ticket) |
| [RVConnectionData] | pConnectionData | Connection info for secure server.<br><br>The Nintendo Switch allows the secure server to be at the same address as the authentication server. In that case, the secure server station url points to  0.0.0.1 with port 1. |
| [String] | strReturnMsg | Server build name |
| [String] | pSourceKey | **Only present on Switch.** If this is a non-empty hex string, key derivation is skipped and this string is used as the key to decrypt the ticket instead. |

# (3) RequestTicket
## Request
| Type | Name | Description |
| --- | --- | --- |
| [PID] | idSource | User pid |
| [PID] | idTarget | Secure server pid |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [Result] | %retval% | Result code |
| [Buffer] | bufResponse | [Kerberos ticket](Kerberos-Authentication.md#kerberos-ticket) |

# (4) GetPID
This is the reverse of the [GetName](#5-getname) method. It looks up the pid that belongs to a given username. The username is not the same as the nintendo network id. On all normal accounts the username is the same as the user pid.

All game servers have a bunch of special users. Normally, the password of the guest account is `MMQea3n!fsik`, but Nintendo seems to have changed this password on all Wii U and 3DS servers except for the friend server. It used to be possible to log in as guest on Switch servers as well, but the guest account has been deleted.

#### 3DS / Wii U:
| PID | Name |
| --- | --- |
| 1 | Quazal Authentication |
| 2 | Quazal Rendez-Vous |
| 100 | guest |
| 101 | Administrator |
| 102 | eval |
| 103 | SandboxProbe |
| 104 | LobbyAdministrator |
| 110 | BackgroundPlayer0 |

#### Switch:
| PID | Name |
| --- | --- |
| 243564795342340018 | Quazal Authentication |
| 257049437023956657 | Quazal Rendez-Vous |
| 564330319085596911 | guest |
| 584465510887342041 | Administrator |
| 621476855497894457 | eval |
| 693188807183308752 | SandboxProbe |
| 1279596992968541952 | LobbyAdministrator |
| 1405107338776927048 | BackgroundPlayer0 |

## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strUserName | Username |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [PID] | %retval% | PID |

# (5) GetName
This is the reverse of the [GetPID](#4-getpid) method. It returns the name associated with the given user pid.

## Request
| Type | Name | Description |
| --- | --- | --- |
| [PID] | id | PID |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [String] | %retval% | Username |

# (6) LoginWithContext
## Request
| Type | Name | Description |
| --- | --- | --- |
| [Any] | loginData | Login data |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [Result] | %retval% | Result code |
| [PID] | pidPrincipal | User pid |
| [Buffer] | pbufResponse | [Kerberos ticket](Kerberos-Authentication.md#kerberos-ticket) |
| [RVConnectionData] | pConnectionData | Connection info for secure server |

# (6) ValidateAndRequestTicketWithParam
## Request
| Type | Description |
| --- | --- |
| [ValidateAndRequestTicketParam](#validateandrequestticketparam-structure) | Param |

### ValidateAndRequestTicketParam ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Platform type (always 3) |
| [String] | Username |
| [Any] | [NullData](#nulldata-structure) or [AuthenticationInfo](#authenticationinfo-structure) |
| Bool | Unknown |
| Uint32 | NEX version (e.g. 40601) |
| Uint32 | Client version |

### NullData ([Structure])
| This structure inherits from [Data] |
| --- |

This struct does not have any fields.

## Response
| Type | Description |
| --- | --- |
| [ValidateAndRequestTicketResult](#validateandrequestticketparam-structure) | result |

### ValidateAndRequestTicketResult ([Structure])
| Type | Description |
| --- | --- |
| [PID] | User id |
| [Buffer] | [Kerberos ticket](Kerberos-Authentication.md#kerberos-ticket) |
| [StationURL] | Secure server location |
| [DateTime] | Server time |
| [String] | Server build name |
| [String] | Kerberos key. If present, key derivation is skipped and this key is used to decrypt the ticket instead. |

[Result]: NEX-Common-Types.md#result
[String]: NEX-Common-Types.md#string
[Buffer]: NEX-Common-Types.md#buffer
[Structure]: NEX-Common-Types.md#structure
[StationURL]: NEX-Common-Types.md#stationurl
[List]: NEX-Common-Types.md#list
[PID]: NEX-Common-Types.md#pid
[DateTime]: NEX-Common-Types.md#datetime
[Data]: NEX-Common-Types.md#data-structure
[Any]: NEX-Common-Types.md#anydataholder
[RVConnectionData]: NEX-Common-Types.md#rvconnectiondata-structure