## [[NEX Protocols]] > [Ranking Protocol (0x70)](Ranking-Protocol) > MK8 Deluxe

This page describes the methods that are only seen in Mario Kart 8 Deluxe.

| Method ID | Method Name |
| --- | --- |
| 16 | GetCompetitionRankingScore |
| 17 | UploadCompetitionRankingScore |
| 18 | [GetCompetitionInfo](#18-getcompetitioninfo) |
| 19 | UploadScorePack |
| 20 | GetScorePack |
| 21 | ExecuteDeleteScoreJob |
| 22 | [GetCommonDataByPIDList](#22-getcommondatabypidlist) |

# (18) GetCompetitionInfo
## Request
| Type | Description |
| --- | --- |
| [GetCompetitionInfoParam](#getcompetitioninfoparam-structure) | Param |

## Request
| Type | Description |
| --- | --- |
| [List]&lt;[CompetitionRankingInfo](#competitionrankinginfo-structure)&gt; | 

# (22) GetCommonDataByPIDList
## Request
| Type | Description |
| --- | --- |
| [List]&lt;[PID]&gt; | Pids |

## Response
| Type | Description |
| --- | --- |
| [CommonDataList](#commondatalist-structure) | Common data |

# Types
## CommonDataList ([Structure])
| Type | Description |
| --- | --- |
| [List]&lt;[qBuffer]&gt; | Common data |

## CompetitionRankingInfo ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| Uint32 | Unknown |
| [List]&lt;Uint32&gt; | Unknown |

## GetCompetitionInfoParam ([Structure])
| Type | Description |
| --- | --- |
| Uint8 | Unknown |
| [ResultRange] | Result range |

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