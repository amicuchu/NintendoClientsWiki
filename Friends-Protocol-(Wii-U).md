## [[NEX Protocols]] > Friends Wii U (0x66)

The following method names are merely guesses, based on what the method does.

| Method ID | Method Name |
| --- | --- |
| 1 | [GetAllInformation](#1-getallinformation) |
| 2 | [GetFriendRequest](#2-getfriendinfo) |
| 3 | [Unknown](#3-unknown) |
| 4 | [Unknown](#4-unknown) |
| 5 | [SendFriendRequest](#5-sendfriendrequest) |
| 6 | [Unknown](#6-unknown) |
| 7 | [Unknown](#7-unknown) |
| 8 | [Unknown](#8-unknown) |
| 9 | [Unknown](#9-unknown) |
| 10 | [Unknown](#10-unknown) |
| 11 | [Unknown](#11-unknown) |
| 12 | [Unknown](#12-unknown) |
| 13 | [UpdatePresence](#13-updatepresence) |
| 14 | [UpdateMii](#14-updatemii) |
| 15 | [UpdateComment](#15-updatecomment) |
| 16 | [Unknown](#16-unknown) |
| 17 | [Unknown](#17-unknown) |
| 18 | [Unknown](#18-unknown) |
| 19 | [Unknown](#19-unknown) |
| 20 | [Unknown](#20-unknown) |

# (1) GetAllInformation
## Request
| Type | Description |
| --- | --- |
| [NNAInfo] | NNA Info |
| [NintendoPresenceV2] | Nintendo presence |
| [DateTime] | Birthday |

## Response
| Type | Description |
| --- | --- |
| [PrincipalPreference] | Principal preference |
| [Comment] | Status message |
| [List]&lt;[FriendInfo]&gt; | Friend list |
| [List]&lt;[FriendRequest]&gt; | Sent friend requests |
| [List]&lt;[FriendRequest]&gt; | Received friend requests |
| [List]&lt;[BlacklistedPrincipal]&gt; | Blacklist |
| Bool | Unknown |
| [List]&lt;[PersistentNotification]&gt; | Notifications |
| Bool | Unknown |

# (2) GetFriendInfo
## Request
| Type | Description |
| --- | --- |
| Uint32 | Unknown |

## Response
| Type | Description |
| --- | --- |
| [FriendRequest] | Friend request |
| [FriendInfo] | Friend info |

# (3) Unknown
## Request
| Type | Description |
| --- | --- |
| [String] | Unknown |

## Response
Unknown

# (4) Unknown
## Request
| Type | Description |
| --- | --- |
| Uint32 | Unknown |

## Response
This method does not return anything.

# (5) SendFriendRequest
## Request
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| Uint8 | Unknown |
| [String] | Unknown |
| Uint8 | Unknown |
| [String] | Unknown |
| [GameKey] | Game key |
| [DateTime] | Unknown |

## Response
Unknown

# (6) Unknown
## Request
| Type | Description |
| --- | --- |
| Uint64 | Unknown |

## Response
This method does not return anthing.

# (7) Unknown
## Request
| Type | Description |
| --- | --- |
| Uint64 | Unknown |

## Response
Unknown

# (8) Unknown
## Request
| Type | Description |
| --- | --- |
| Uint64 | Unknown |

## Response
This method does not return anything.

# (9) Unknown
## Request
| Type | Description |
| --- | --- |
| Uint64 | Unknown |

## Response
Unknown

# (10) Unknown
## Request
| Type | Description |
| --- | --- |
| [List]&lt;Uint64&gt; | Unknown |

## Response
This method does not return anything.

# (11) Unknown
## Request
| Type | Description |
| --- | --- |
| [BlacklistedPrincipal] | Unknown |

## Response
Unknown

# (12) Unknown
## Request
| Type | Description |
| --- | --- |
| Uint32 | Unknown |

## Response
This method does not return anything.

# (13) UpdatePresence
## Request
| Type | Description |
| --- | --- |
| [NintendoPresenceV2] | Nintendo presence |

## Response
This method does not return anything.

# (14) UpdateMii
## Request
| Type | Description |
| --- | --- |
| [MiiV2] | Mii |

## Response
Unknown

# (15) UpdateComment
## Request
| Type | Description |
| --- | --- |
| [Comment] | Status message |

## Response
Unknown

# (16) Unknown
## Request
| Type | Description |
| --- | --- |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |

## Response
This method does not return anything.

# (17) Unknown
## Request
| Type | Description |
| --- | --- |
| [List]&lt;Uint32&gt; | Unknown |

# (18) Unknown
## Request
| Type | Description |
| --- | --- |
| [List]&lt;[PersistentNotification]&gt; | Unknown |

## Response
This method does not return anything.

## Response
Unknown

# Types
## BlacklistedPrincipal
| Type | Description |
| --- | --- |
| [PrincipalBasicInfo] | Principal basic info |
| [GameKey] | Game key |
| [DateTime] | Blacklisted since |

## Comment
| Type | Description |
| --- | --- |
| Uint8 | Unknown |
| [String] | Status message |
| [DateTime] | Last changed on |

## FriendInfo
| Type | Description |
| --- | --- |
| [NNAInfo] | NNA Info |
| [NintendoPresenceV2] | Nintendo presence |
| [Comment] | Status message |
| [DateTime] | Became friend |
| [DateTime] | Last online |
| Uint64 | Unknown |

## FriendRequest
| Type | Description |
| --- | --- |
| [PrincipalBasicInfo] | Principal basic info |
| [FriendRequestMessage] | Message |
| [DateTime] | Sent on |

## FriendRequestMessage
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| [String] | Message |
| Uint8 | Unknown |
| [String] | Unknown |
| [GameKey] | Game key |
| [DateTime] | Unknown |
| [DateTime] | Expires on |

## GameKey
| Type | Description |
| --- | --- |
| Uint64 | Title id |
| Uint16 | Title version |

## MiiV2
| Type | Description |
| --- | --- |
| [String] | Name |
| Uint8 | Unknown |
| Uint8 | Unknown |
| [Buffer] | Mii data (FFLStoreData) |
| [DateTime] | Unknown |

## NintendoPresenceV2
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| Bool | Is online |
| [GameKey] | Game key |
| Uint8 | Unknown |
| [String] | Message |
| Uint32 | Unknown |
| Uint8 | Unknown |
| Uint32 | Game server id |
| Uint32 | Unknown |
| Uint32 | Pid |
| Uint32 | Gathering id |
| [Buffer] | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |

## NNAInfo
| Type | Description |
| --- | --- |
| [PrincipalBasicInfo] | Principal basic info |
| Uint8 | Unknown |
| Uint8 | Unknown |

## PersistentNotification
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| [String] | Unknown |

## PrincipalBasicInfo
| Type | Description |
| --- | --- |
| Uint32 | Pid |
| [String] | NNID |
| [MiiV2] | Mii |
| Uint8 | Unknown |

## PrincipalPreference
| Type | Description |
| --- | --- |
| Bool | Unknown |
| Bool | Unknown |
| Bool | Unknown |

[BlacklistedPrincipal]: #blacklistedprincipal
[Comment]: #comment
[FriendInfo]: #friendinfo
[FriendRequest]: #friendrequest
[FriendRequestMessage]: #friendrequestmessage
[GameKey]: #gamekey
[MiiV2]: #miiv2
[NintendoPresenceV2]: #nintendopresencev2
[NNAInfo]: #nnainfo
[PersistentNotification]: #persistentnotification
[PrincipalBasicInfo]: #principalbasicinfo
[PrincipalPreference]: #principalpreference

[DateTime]: NEX-Common-Types#date-time
[List]: NEX-Common-Types#list
[String]: NEX-Common-Types#string
[Buffer]: NEX-Common-Types#buffer