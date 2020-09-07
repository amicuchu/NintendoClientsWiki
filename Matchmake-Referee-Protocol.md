## [[NEX Protocols]] > Matchmake Referee (0x78)

| Method ID | Method Name |
| --- | --- |
| 1 | [StartRound](#1-startround) |
| 2 | GetStartRoundParam |
| 3 | [EndRound](#3-endround) |
| 4 | [EndRoundWithPartialReport](#4-endroundwithpartialreport) |
| 5 | [EndRoundWithoutReport](#5-endroundwithoutreport) |
| 6 | GetRoundParticipants |
| 7 | GetNotSummarizedRound |
| 8 | GetRound |
| 9 | GetStatsPrimary |
| 10 | GetStatsPrimaries |
| 11 | GetStatsAll |
| 12 | CreateStats |
| 13 | GetOrCreateStats |
| 14 | [ResetStats](#14-resetstats) |
| 15 | GetEventPoint |
| 16 | ResetEventPoint |

# (1) StartRound
## Request
| Type | Description |
| --- | --- |
| [MatchmakeRefereeStartRoundParam](#matchmakerefereestartroundparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| Uint64 | Round id |

# (3) EndRound
## Request
| Type | Description |
| --- | --- |
| [MatchmakeRefereeEndRoundParam](#matchmakerefereeendroundparam-structure) | Param |

## Response
This method does not return anything.

# (4) EndRoundWithPartialReport
## Request
| Type | Description |
| --- | --- |
| [MatchmakeRefereeEndRoundParam](#matchmakerefereeendroundparam-structure) | Param |

## Response
This method does not return anything.

# (5) EndRoundWithoutReport
## Request
| Type | Description |
| --- | --- |
| Uint64 | Round id |

## Response
This method does not return anything.

# (14) ResetStats
## Request
This method does not take any parameters.

## Response
This method does not return anything.

# Types
## MatchmakeRefereeEndRoundParam ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Round id |
| [List]&lt;[EndRoundReport](#endroundreport-structure)&gt; | Reports |

## EndRoundReport ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| [qBuffer] | Unknown |
| Uint8 | Unknown |
| Uint32 | Unknown |

## MatchmakeRefereeStartRoundParam ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| Uint32 | Gathering id |
| [List]&lt;[PID]&gt; | User ids |
| Uint8 | Unknown |
| Uint32 | Unknown |

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
