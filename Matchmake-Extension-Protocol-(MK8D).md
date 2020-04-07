## [[NEX Protocols]] > [Matchmake Extension (0x6D)](Matchmake-Extension-Protocol) > MK8 Deluxe

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

[SimplePlayingSession]: Match-Making-Types#simpleplayingsession-structure

[Result]: NEX-Common-Types#result
[String]: NEX-Common-Types#string
[Buffer]: NEX-Common-Types#buffer
[qBuffer]: NEX-Common-Types#qbuffer
[List]: NEX-Common-Types#list
[Map]: NEX-Common-Types#map
[DateTime]: NEX-Common-Types#datetime
[Structure]: NEX-Common-Types#structure
[Data]: NEX-Common-Types#anydataholder
[PID]: NEX-Common-Types#pid
[ResultRange]: NEX-Common-Types#resultrange-structure