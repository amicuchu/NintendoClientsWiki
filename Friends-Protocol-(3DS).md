## [[NEX Protocols]] > Friends 3DS (0x65)

| Method ID | Method Name |
| --- | --- |
| 1 | [UpdateProfile](#1-updateprofile) |
| 2 | [UpdateMii](#2-updatemii) |
| 3 | [UpdateMiiList](#3-updatemiilist) |
| 4 | [UpdatePlayedGames](#4-updateplayedgames) |
| 5 | [UpdatePreference](#5-updatepreference) |
| 6 | [GetFriendMii](#6-getfriendmii) |
| 7 | [GetFriendMiiList](#7-getfriendmiilist) |
| 8 | ? |
| 9 | ? |
| 10 | [GetFriendRelationships](#10-getfriendrelationships) |
| 11 | [AddFriendByPrincipalID](#11-addfriendbyprincipalid) |
| 12 | ? |
| 13 | ? |
| 14 | ? |
| 15 | [GetAllFriends](#15-getallfriends) |
| 16 | ? |
| 17 | [SyncFriend](#17-syncfriend) |
| 18 | [UpdatePresence](#18-updatepresence) |
| 19 | [UpdateFavoriteGameKey](#19-updatefavoritegamekey)  |
| 20 | [UpdateComment](#20-updatecomment) |
| 21 | ? |
| 22 | [GetFriendPresence](#22-getfriendpresence) |
| 23 | ? |
| 24 | [GetFriendPicture](#24-getfriendpicture) |
| 25 | [GetFriendPersistentInfo](#25-getfriendpersistentinfo) |
| 26 | ? |

# (1) UpdateProfile
## Request
| Type | Description |
| --- | --- |
| [MyProfile](#myprofile) | Profile data |

## Response
This method does not return anything

# (2) UpdateMii
## Request
| Type | Description |
| --- | --- |
| [Mii](#mii) | Mii |

## Response
This method does not return anything

# (3) UpdateMiiList
## Request
| Type | Description |
| --- | --- |
| [MiiList](#miilist) | Mii list |

## Response
This method does not return anything.

# (4) UpdatePlayedGames
## Request
| Type | Description |
| --- | --- |
| [List]&lt;[PlayedGame](#playedgame)&gt; | Played games |

## Response
This method does not return anything.

# (5) UpdatePreference
## Request
| Type | Description |
| --- | --- |
| Bool | Unknown |
| Bool | Unknown |
| Bool | Unknown |

## Response
This method does not return anything

# (6) GetFriendMii
## Request
| Type | Description |
| --- | --- |
| [List]&lt;[FriendMiiRequest](#friendmiirequest)&gt; | Friends |

## response
| Type | Description |
| --- | --- |
| [List]&lt;[FriendMii](#friendmii)&gt; | Miis |

# (7) GetFriendMiiList
## Request
| Type | Description |
| --- | --- |
| [List]&lt;[FriendMiiRequest](#friendmiirequest)&gt; | Friends |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[FriendMiiList](#friendmiilist)&gt; | Mii lists |

# (10) GetFriendRelationships
## Request
| Type | Description |
| --- | --- |
| [List]&lt;Uint32&gt; | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[FriendRelationship](#friendrelationship)&gt; | Friend relationships |

# (11) AddFriendByPrincipalID
## Request
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Uint32 | Principal id |

## Response
| Type | Description |
| --- | --- |
| [FriendRelationship](#friendrelationship) | Friend relationship |

# (15) GetAllFriends
## Request
This method does not take any request data.

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[FriendRelationship](#friendrelationship)&gt; | Friend relationships |

# (17) SyncFriend
## Request
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| [List]&lt;Uint32&gt; | Unknown |
| [List]&lt;Uint64&gt; | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[FriendRelationship](#friendrelationship)&gt; | Friend list |

# (18) UpdatePresence
## Request
| Type | Description |
| --- | --- |
| [NintendoPresence](#nintendopresence) | Presence info |
| Bool | Unknown |

## Response
This method does not return anything

# (19) UpdateFavoriteGameKey
## Request
| Type | Description |
| --- | --- |
| [GameKey](#gamekey) | Game key |

## Response
This method does not return anything.

# (20) UpdateComment
## Request
| Type | Description |
| --- | --- |
| [String] | Comment |

## Response
This method does not return anything

# (22) GetFriendPresence
## Request
| Type | Description |
| --- | --- |
| [List]&lt;Uint32&gt; | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[FriendPresence](#friendpresence)&gt; | Friend presence list |

# (24) GetFriendPicture
## Request
| Type | Description |
| --- | --- |
| [List]&lt;Uint32&gt; | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[FriendPicture](#friendpicture)&gt; | Friend pictures |

# (25) GetFriendPersistentInfo
## Request
| Type | Description |
| --- | --- |
| [List]&lt;Uint32&gt; | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[FriendPersistentInfo](#friendpersistentinfo)&gt; | Persistent info |

# Types
## FriendMii
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| [Mii](#mii) | Mii |
| [DateTime] | Unknown |

## FriendMiiList
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| [MiiList](#miilist) | Mii list |
| [DateTime] | Unknown |

## FriendMiiRequest
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| [DateTime] | Unknown |

## FriendPersistentInfo
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| Uint8 | Region |
| Uint8 | Country |
| Uint8 | Area |
| Uint8 | Language |
| Uint8 | Platform |
| [GameKey](#gamekey) | Game key |
| [String] | Unknown |
| [DateTime] | Unknown |
| [DateTime] | Unknown |
| [DateTime] | Unknown |

## FriendPicture
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| [Buffer] | Data |
| [DateTime] | Date time |

## FriendPresence
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| [NintendoPresence](#nintendopresence) | Nintendo presence |

## FriendRelationship
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| Uint64 | Unknown |
| Uint8 | Unknown |

## GameKey
| Type | Description |
| --- | --- |
| Uint64 | Title id |
| Uint16 | Title version |

## Mii
| Type | Description |
| --- | --- |
| [String] | Unknown |
| Bool | Unknown |
| Uint8 | Unknown |
| [Buffer] | Mii data |

## MiiList
| Type | Description |
| --- | --- |
| [String] | Unknown |
| Bool | Unknown |
| Uint8 | Unknown |
| [List]&lt;[Buffer]&gt; | Mii data list |

## MyProfile
| Type | Description |
| --- | --- |
| Uint8 | Region |
| Uint8 | Country |
| Uint8 | Area |
| Uint8 | Language |
| Uint8 | Platform |
| Uint64 | Unknown |
| [String] | Unknown |
| [String] | Unknown |

## NintendoPresence
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | m_changedBitFlag |
| [GameKey](#gamekey) | m_gameKey | Game key |
| [String] | m_gameModeDescription | Message |
| Uint32 | m_joinAvailabilityFlag | |
| Uint8 | m_matchmakeSystemType | |
| Uint32 | m_joinGameID | |
| Uint32 | m_joinGameMode | |
| [PID] | m_ownerPrincipalID | |
| Uint32 | m_joinGroupID | |
| [Buffer] | m_applicationArg | |

## PlayedGame
| Type | Description |
| --- | --- |
| [GameKey](#gamekey) | Game key |
| [DateTime] | Date time |

[String]: NEX-Common-Types#string
[List]: NEX-Common-Types#list
[Buffer]: NEX-Common-Types#buffer
[DateTime]: NEX-Common-Types#date-time
[PID]: NEX-Common-Types#pid