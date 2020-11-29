## [NEX Protocols](NEX-Protocols.md) > [Matchmake Extension (0x6D)](Matchmake-Extension-Protocol.md) > Monster Hunter XX
This page describes the methods that are only seen in Monster Hunter XX (3DS).

| Method ID | Method Name |
| --- | --- |
| 54 | [UpdateFriendUserProfile](#54-updatefrienduserprofile) |
| 55 | [GetFriendUserProfiles](#55-getfrienduserprofiles) |
| 56 | [GetFriends](#56-getfriends) |
| 57 | [AddFriends](#57-addfriends) |
| 58 | [RemoveFriend](#58-removefriend) |
| 59 | [FindCommunityByOwner](#59-findcommunitybyowner) |

# (54) UpdateFriendUserProfile
## Request
| Type | Name |
| --- | --- |
| [FriendUserParam] | param |

## Response
This method does not return anything.

# (55) GetFriendUserProfiles
## Request
| Type | Name |
| --- | --- |
| [List]&lt;Uint64&gt; | pids |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[FriendUserInfo]&gt; | infos |

# (56) GetFriends
## Request
This method does not take any parameters.

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[FriendUserInfo]&gt; | infos |

# (57) AddFriends
## Request
| Type | Name |
| --- | --- |
| [List]&lt;Uint64&gt; | pids |

## Response
This method does not return anything.

# (58) RemoveFriend
## Request
| Type | Name |
| --- | --- |
| Uint64 | pid |

## Response
This method does not return anything.

# (59) FindCommunityByOwner
## Request
| Type | Name |
| --- | --- |
| Uint64 | id |
| [ResultRange](NEX-Common-Types.md#resultrange-structure) | resultRange |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[PersistentGathering]&gt; | lstCommunity |

# Types
## FriendUserParam ([Structure])
| Type | Name |
| --- | --- |
| [String] | name |

## FriendUserInfo ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | pid |
| [String] | name |
| Uint32 | presence |

[Result]: NEX-Common-Types.md#result
[String]: NEX-Common-Types.md#string
[Buffer]: NEX-Common-Types.md#buffer
[qBuffer]: NEX-Common-Types.md#qbuffer
[List]: NEX-Common-Types.md#list
[Map]: NEX-Common-Types.md#map
[DateTime]: NEX-Common-Types.md#date-time
[Structure]: NEX-Common-Types.md#structure
[Data]: NEX-Common-Types.md#any-data-holder
[Variant]: NEX-Common-Types.md#variant

[MatchmakeSessionSearchCriteria]: #matchmakesessionsearchcriteria-structure
[PlayingSession]: #playingsession-structure
[PersistentGathering]: #persistentgathering-structure
[SimplePlayingSession]: #simpleplayingsession-structure
[SimpleCommunity]: #simplecommunity-structure
[CreateMatchmakeSessionParam]: #creatematchmakesessionparam-structure
[MatchmakeSession]: #matchmakesession-structure
[JoinMatchmakeSessionParam]: #joinmatchmakesessionparam-structure
[AutoMatchmakeParam]: #automatchmakeparam-structure
[UpdateMatchmakeSessionParam]: #updatematchmakesessionparam-structure
[FindMatchmakeSessionByParticipantParam]: #findmatchmakesessionbyparticipantparam-structure
[FindMatchmakeSessionByParticipantResult]: #findmatchmakesessionbyparticipantresult-structure
[FriendUserParam]: #frienduserparam-structure
[FriendUserInfo]: #frienduserinfo-structure
[MatchmakeParam]: #matchmakeparam-structure
[MatchmakeBlockListParam]: #matchmakeblocklistparam-structure