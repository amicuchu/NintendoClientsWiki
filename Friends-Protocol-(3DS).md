## [[NEX Protocols]] > Friends 3DS (0x65)

| Method ID | Method Name |
| --- | --- |
| 1 | [UpdateProfile](#1-updateprofile) |
| 2 | [UpdateMii](#2-updatemii) |
| 3 | [UpdateMiiList](#3-updatemiilist) |
| 4 | [UpdatePlayedGames](#4-updateplayedgames) |
| 5 | [UpdatePreference](#5-updatepreference) |
| 6 | GetFriendMii |
| 7 | ? |
| 8 | ? |
| 9 | GetPrincipalIDByLocalFriendCode |
| 10 | ? |
| 11 | [AddFriendByPrincipalID](#addfriendbyprincipalid) |
| 12 | ? |
| 13 | ? |
| 14 | ? |
| 15 | ? |
| 16 | ? |
| 17 | [SyncFriend](#17-syncfriend) |
| 18 | [UpdatePresence](#18-updatepresence) |
| 19 | [UpdateFavoriteGameKey](#19-updatefavoritegamekey)  |
| 20 | [UpdateComment](#20-updatecomment) |
| 21 | ? |
| 22 | GetPresence |
| 23 | ? |
| 24 | ? |
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

# (25) GetFriendPersistentInfo
## Request
| Type | Description |
| --- | --- |
| [List]&gt;Uint32&gt; | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[FriendPersistentInfo](#friendpersistentinfo)&gt; | Persistent info |

# Types
## FriendPersistentInfo
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| [GameKey](#gamekey) | Game key |
| [String] | Unknown |
| [DateTime] | Unknown |
| [DateTime] | Unknown |
| [DateTime] | Unknown |

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
| Uint8 | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Uint64 | Unknown |
| [String] | Unknown |
| [String] | Unknown |

## NintendoPresence
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| [GameKey](#gamekey) | Game key |
| [String] | Message |
| Uint32 | Unknown |
| Uint8 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| [Buffer] | Unknown |

## PlayedGame
| Type | Description |
| --- | --- |
| [GameKey](#gamekey) | Game key |
| [DateTime] | Date time |

[String]: NEX-Common-Types#string
[List]: NEX-Common-Types#list
[Buffer]: NEX-Common-Types#buffer
[DateTime]: NEX-Common-Types#date-time