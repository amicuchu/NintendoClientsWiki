## [[NEX Protocols]] > Ranking 2 (0x7A)

| Method ID | Method Name |
| --- | --- |
| 1 | PutScore |
| 2 | GetCommonData |
| 3 | PutCommonData |
| 4 | DeleteCommonData |
| 5 | [GetRanking](#5-getranking) |
| 6 | GetRankingByPrincipalId |
| 7 | GetCategorySetting |

# (5) GetRanking
## Request
| Type | Description |
| --- | --- |
| [Ranking2GetParam](#ranking2getparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [Ranking2Info](#ranking2info) | Rankings |

# Types
## Ranking2GetParam ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |

## Ranking2Info ([Structure])
| Type | Description |
| --- | --- |
| [List]&lt;[Ranking2RankData](#ranking2rankdata-structure)&gt; | Rank data |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Sint32 | Unknown |

## Ranking2RankData ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Uint64 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| [Ranking2CommonData](#ranking2commondata-structure) | Common data |

## Ranking2CommonData ([Structure])
| Type | Description |
| --- | --- |
| [String] | Unknown |
| [Buffer] | Unknown |
| [Buffer] | Unknown |

[Result]: NEX-Common-Types#result
[String]: NEX-Common-Types#string
[Buffer]: NEX-Common-Types#buffer
[qBuffer]: NEX-Common-Types#qbuffer
[List]: NEX-Common-Types#list
[Map]: NEX-Common-Types#map
[DateTime]: NEX-Common-Types#date-time
[Structure]: NEX-Common-Types#structure
[Data]: NEX-Common-Types#any-data-holder
[PID]: NEX-Common-Types#pid
[ResultRange]: NEX-Common-Types#result-range-structure