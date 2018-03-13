## [[NEX Protocols]] > Friends 3DS (0x65)

| Method ID | Method Name |
| --- | --- |
| 1 | [UpdateProfile](#1-updateprofile) |
| 2 | UpdateMii |
| 3 | ? |
| 4 | ? |
| 5 | UpdatePreference |
| 6 | GetMii |
| 7 | ? |
| 8 | ? |
| 9 | GetPrincipalIDByLocalFriendCode |
| 10 | ? |
| 11 | AddFriendByPrincipalID |
| 12 | ? |
| 13 | ? |
| 14 | ? |
| 15 | ? |
| 16 | ? |
| 17 | [SyncFriend](#17-syncfriend) |
| 18 | [UpdatePresence](#18-updatepresence) |
| 19 | UpdateFavoriteGameKey  |
| 20 | UpdateComment |
| 21 | ? |
| 22 | GetPresence |
| 23 | ? |
| 24 | ? |
| 25 | GetPersistentInfo |
| 26 | ? |

# (1) UpdateProfile
## Request
| Type | Description |
| --- | --- |
| [MyProfile](#myprofile) | Profile data |

## Response
This method does not return anything

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
This method does not return anything.

#Types
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
| Uint32 | Game server id? |
| Uint32 | Unknown |
| Uint32 | User pid? |
| Uint32 | Gathering id? |
| [Buffer] | Unknown |

[String]: NEX-Common-Types#string
[List]: NEX-Common-Types#list
[Buffer]: NEX-Common-Types#buffer