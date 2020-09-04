## [[NEX Protocols]] > Matchmake Referee (0x78)

| Method ID | Method Name |
| --- | --- |
| 1 | [StartRound](#1-startround) |
| 2 | GetStartRoundParam |
| 3 | [EndRound](#3-endround) |
| 4 | [EndRoundWithPartialReport](#4-endroundwithpartialreport) |
| 5 | [GetRoundParticipants](#5-getroundparticipants) |
| 6 | GetNotSummarizedRound |
| 7 | GetRound |
| 8 | GetStatsPrimary |
| 9 | GetStatsPrimaries |
| 10 | GetStatsAll |
| 11 | CreateStats |
| 12 | GetOrCreateStats |

# (1) StartRound
## Request
| Type | Description |
| --- | --- |
| [StartRoundParam](#startroundparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| Uint64 | Unknown |

# (3) EndRound
## Request
| Type | Description |
| --- | --- |
| [EndRoundParam](#endroundparam-structure) | Param |

## Response
This method does not return anything.

# (4) EndRoundWithPartialReport
## Request
| Type | Description |
| --- | --- |
| [EndRoundParam](#endroundparam-structure) | Param |

## Response
This method does not return anything.

# (5) GetRoundParticipants
## Request
| Type | Description |
| --- | --- |
| Uint64 | Unknown |

## Response
This method does not return anything.

# Types
## EndRoundInfo ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| [qBuffer] | Unknown |
| Uint8 | Unknown |
| Uint32 | Unknown |

## EndRoundParam ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| [List]&lt;[EndRoundInfo](#endroundinfo-structure)&gt; | Unknown |

## StartRoundParam ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| Uint32 | Unknown |
| [List]&lt;Uint64&gt; | Unknown |
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
