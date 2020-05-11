[[NEX Protocols]] > Simple Authentication (0x10)
---

Interestingly, this protocol has `Cafe` in some of its method names, even though this protocol is never used by Nintendo.

| Method ID | Method Name |
| --- | --- |
| 1 | Authenticate |
| 2 | [LoginWithToken](#2-loginwithtoken) |
| 3 | [LoginWithTokenEx](#3-loginwithtokenex) |
| 4 | Login |
| 5 | LoginWithSubAccount |
| 6 | Register |
| 7 | RegisterEx |
| 8 | LoginWithTokenCafe |
| 9 | LoginWithTokenCafeEx |

# (2) LoginWithToken
## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strToken | Token |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [Result] | %retval% | Result code |
| Uint32 | pidPrincipal | Pid |
| [RVConnectionData] | pConnectionData | Connection info for secure server |
| [String] | strReturnMsg | Response message |

# (3) LoginWithTokenEx
## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strToken | Token |
| [RVConnectionData] | pConnectionData | Connection info for secure server |
| [Data] | oAnyData | Login data |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [Result] | %retval% | Result code |
| Uint32 | pidPrincipal | User pid |
| [RVConnectionData] | pConnectionData | Connection info for secure server |
| [String] | strReturnMsg | Response message |

[Result]: NEX-Common-Types#result
[String]: NEX-Common-Types#string
[Data]: NEX-Common-Types#anydataholder
[RVConnectionData]: NEX-Common-Types#rvconnectiondata-structure