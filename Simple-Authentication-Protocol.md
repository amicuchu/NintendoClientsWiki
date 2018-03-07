[[NEX Protocols]] > Simple Authentication (0x10)
---

Interestingly, this protocol has methods referencing the Wii U, even though this protocol is never used by Nintendo games.

| Method ID | Method Name |
| --- | --- |
| 1 | [Authenticate](#1-authenticate) |
| 2 | [LoginWithToken](#2-loginwithtoken) |
| 3 | [LoginWithTokenEx](#3-loginwithtokenex) |
| 4 | [Login](#4-login) |
| 5 | [LoginWithSubAccount](#5-loginwithsubaccount) |
| 6 | [Register](#6-register) |
| 7 | [RegisterEx](#7-registerex) |
| 8 | [LoginWithTokenCafe](#8-loginwithtokencafe) |
| 9 | [LoginWithTokenCafeEx](#9-loginwithtokencafeex) |

# (1) Authenticate
# (2) LoginWithToken
# (3) LoginWithTokenEx
## Request
| Type | Description |
| --- | --- |
| [String] | Token |
| [RVConnectionData](NEX-Common-Types#rendez-vous-connection-data-structure) | Connection info for secure server |
| [Data] | Login data |

## Response
| Type | Description |
| --- | --- |
| Uint32 | Result code |
| Uint32 | User pid |
| [RVConnectionData](NEX-Common-Types#rendez-vous-connection-data-structure) | Connection info for secure server |
| [String] | Response message |

# (4) Login
# (5) LoginWithSubAccount
# (6) Register
# (7) RegisterEx
# (8) LoginWithTokenCafe
# (9) LoginWithTokenCafeEx

[String]: NEX-Common-Types#string
[Data]: NEX-Common-Types#any-data-holder