## [NEX Protocols](NEX-Protocols.md) > [Matchmake Extension (0x6D)](Matchmake-Extension-Protocol.md) > MK8 Deluxe

This page describes the methods that are only seen in Mario Kart 8 Deluxe.

| Method ID | Method Name |
| --- | --- |
| 54 | CreateSimpleSearchObject |
| 55 | UpdateSimpleSearchObject |
| 56 | DeleteSimpleSearchObject |
| 57 | SearchSimpleSearchObject |
| 58 | SearchSimpleSearchObjectByObjectIds |
| 59 | JoinMatchmakeSessionWithExtraParticipants |
| 60 | [CustomGetSimplePlayingSession](#60-customgetsimpleplayingsession) |
| 61 | CreateCompetition |
| 62 | DeleteCompetition |
| 63 | RegisterFavoriteCompetition |
| 64 | UnregisterFavoriteCompetition |
| 65 | GetFavoriteCompetition |
| 66 | GetTeamParticipants |
| 67 | FindCommunityByOwner |

# (60) CustomGetSimplePlayingSession
## Request
| Type | Description |
| --- | --- |
| [List]&lt;[PID]&gt; | Pids |
| Uint8 | Unknown |
| Uint8 | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[SimplePlayingSession]&gt; | Playing sessions |

[SimplePlayingSession]: Match-Making-Types.md#simpleplayingsession-structure

[Result]: NEX-Common-Types.md#result
[String]: NEX-Common-Types.md#string
[Buffer]: NEX-Common-Types.md#buffer
[qBuffer]: NEX-Common-Types.md#qbuffer
[List]: NEX-Common-Types.md#list
[Map]: NEX-Common-Types.md#map
[DateTime]: NEX-Common-Types.md#datetime
[Structure]: NEX-Common-Types.md#structure
[Data]: NEX-Common-Types.md#anydataholder
[PID]: NEX-Common-Types.md#pid
[ResultRange]: NEX-Common-Types.md#resultrange-structure