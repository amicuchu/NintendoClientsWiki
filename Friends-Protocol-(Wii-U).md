## [[NEX Protocols]] > Friends Wii U (0x66)

The following method names are merely guesses, based on what the method does.

| Method ID | Method Name |
| --- | --- |
| 1 | [GetAllInformation](#1-getallinformation) |
| 2 | ? |
| 3 | ? |
| 4 | ? |
| 5 | ? |
| 6 | ? |
| 7 | ? |
| 8 | ? |
| 9 | ? |
| 10 | ? |
| 11 | ? |
| 12 | ? |
| 13 | [UpdatePresence](#13-updatepresence) |
| 14 | ? |
| 15 | ? |
| 16 | ? |
| 17 | ? |
| 18 | ? |
| 19 | ? |
| 20 | ? |

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

# (13) UpdatePresence
## Request
| Type | Description |
| --- | --- |
| [NintendoPresenceV2] | Nintendo presence |

## Response
This method does not return anything.

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