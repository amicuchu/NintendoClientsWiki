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
| 18 | UpdatePresence |
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
| [Data]&lt;[MyProfile](#myprofile)&gt; | Profile data |

### MyProfile
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

## Response
This method does not return anything

[String]: NEX-Common-Types#string
[List]: NEX-Common-Types#list
[Data]: NEX-Common-Types#any-data-holder

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
| [List]&lt;[Data]&lt;[FriendRelationship](#friendrelationship)&gt;&gt; | Friend list |

# FriendRelationship
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| Uint64 | Unknown |
| Uint8 | Unknown |