## [[NEX Protocols]] > Ranking (0x70)

| Method ID | Method Name |
| --- | --- |
| 1 | [UploadScore](#1-uploadscore) |
| 2 | [DeleteScore](#2-deletescore) |
| 3 | [DeleteAllScores](#3-deleteallscores) |
| 4 | [UploadCommonData](#4-uploadcommondata) |
| 5 | [DeleteCommonData](#5-deletecommondata) |
| 6 | [GetCommonData](#6-getcommondata) |
| 7 | [ChangeAttributes](#7-changeattributes) |
| 8 | [ChangeAllAttributes](#8-changeallattributes) |
| 9 | [GetRanking](#9-getranking) |
| 10 | [GetApproxOrder](#10-getapproxorder) |
| 11 | [GetStats](#11-getstats) |
| 12 | [GetRankingByPIDList](#12-getrankingbypidlist) |
| 13 | [GetRankingByUniqueIdList](#13-getrankingbyuniqueidlist) |
| 14 | [GetCachedTopXRanking](#14-getcachedtopxranking) |
| 15 | [GetCachedTopXRankings](#15-getcachedtopxrankings) |

# (1) UploadScore
## Request
| Type | Name | Description |
| --- | --- | --- |
| [RankingScoreData](#rankingscoredata-structure) | scoreData | Score data |
| Uint64 | uniqueId | |

## Response
This method does not return anything.

# (2) DeleteScore
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | category | Category (game-specific) |
| Uint64 | uniqueId | |

## Response
This method does not return anything.

# (3) DeleteAllScores
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint64 | uniqueId | |

## Response
This method does not return anything.

# (4) UploadCommonData
## Request
| Type | Name | Description |
| --- | --- | --- |
| [Buffer] | commonData | Data |
| Uint64 | uniqueId | Data id |

## Response
This method does not return anything.

# (5) DeleteCommonData
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint64 | uniqueId | Data id |

## Response
This method does not return anything.

# (6) GetCommonData
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint64 | uniqueId | Data id |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [Buffer] | commonData | Data |

# (7) ChangeAttributes
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | category | Category |
| [RankingChangeAttributesParam](#rankingchangeattributesparam-structure) | changeParam | |
| Uint64 | uniqueId | |

## Response
This method does not return anything.

# (8) ChangeAllAttributes
## Request
| Type | Name | Description |
| --- | --- | --- |
| [RankingChangeAttributesParam](#rankingchangeattributesparam-structure) | changeParam | |
| Uint64 | uniqueId | |

# (9) GetRanking
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint8 | rankingMode | [Ranking mode](#ranking-mode) |
| Uint32 | category | Category (game-specific) |
| [RankingOrderParam](#rankingorderparam-structure) | orderParam | A bunch of parameters |
| Uint64 | uniqueId | |
| [PID] | principalId | |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [RankingResult](#rankingresult-structure) | pResult | The result |

# (10) GetApproxOrder
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | category | |
| [RankingOrderParam](#rankingorderparam-structure) | orderParam | |
| Uint32 | score | |
| Uint64 | uniqueId | |
| Uint32 | principalId | |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | pOrder | |

# (11) GetStats
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | category | |
| [RankingOrderParam](#rankingorderparam-structure) | orderParam | |
| Uint32 | flags | Specifies the kind of stats returned |

### Flags
| Value | Description |
| --- | --- |
| 0x1 | Number of ranking entries |
| 0x2 | Sum of all scores |
| 0x4 | Lowest score |
| 0x8 | Highest score |
| 0x10 | Average score |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [RankingStats](#rankingstats-structure) | pStats | |

# (12) GetRankingByPIDList
## Request
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[PID]&gt; | principalIdList | User ids |
| Uint8 | rankingMode | [Ranking mode](#ranking-mode) |
| Uint32 | category | |
| [RankingOrderParam](#rankingorderparam-structure) | orderParam | |
| Uint64 | uniqueId | |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [RankingResult](#rankingresult-structure) | pResult | Result |

# (13) GetRankingByUniqueIdList
## Request
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;Uint64&gt; | nexUniqueIdList | |
| Uint8 | rankingMode | [Ranking mode](#ranking-mode) |
| Uint32 | category | |
| [RankingOrderParam](#rankingorderparam-structure) | orderParam | |
| Uint64 | uniqueId | |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [RankingResult](#rankingresult-structure) | pResult | Result |

# (14) GetCachedTopXRanking
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | category | |
| [RankingOrderParam](#rankingorderparam-structure) | orderParam | |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [RankingCachedResult](#rankingcachedresult-inherits-rankingresult) | pResult | Result |

# (15) GetCachedTopXRankings
## Request
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;Uint32&gt; | categories | |
| [List]&lt;[RankingOrderParam](#rankingorderparam-structure)&gt; | orderParams | |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[RankingCachedResult](#rankingcachedresult-inherits-rankingresult)&gt; | pResults | |

# Types
## RankingOrderParam ([Structure])
| Type | Name | Description |
| --- | --- | --- |
| Uint8 | orderCalculation | Rank calculation |
| Uint8 | groupIndex | Filter index |
| Uint8 | groupNum | Filter number |
| Uint8 | timeScope | Time scope |
| Uint32 | offset | Base rank (0 is world record) |
| Uint8 | length | Desired number of rankings |

#### Rank Calculation
| Value | Description |
| --- | --- |
| 0 | Standard ranking (1224) |
| 1 | Ordinal ranking (1234) |

## RankingRankData ([Structure])
| Type | Name | Description |
| --- | --- | --- |
| [PID] | principalId | User id |
| Uint64 | uniqueId | |
| Uint32 | order | Rank |
| Uint32 | category | Category |
| Uint32 | score | Score |
| [List]&lt;byte&gt; | groups | Filters |
| Uint64 | param | Additional info |
| [Buffer] | commonData | Additional data |

## RankingResult ([Structure])
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[RankingRankData](#rankingrankdata-structure)&gt; | rankDataList | Rankings |
| Uint32 | totalCount | Total number of ranking entries on the server |
| [DateTime] | sinceTime | |

## RankingCachedResult (Inherits [RankingResult](#rankingresult))
| Type | Name | Description |
| --- | --- | --- |
| [DateTime] | createdTime | |
| [DateTime] | expiredTime | |
| Uint8 | maxLength | |

## RankingStats ([Structure])
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;Double&gt; | statsList | Stats |

## RankingScoreData ([Structure])
| Type | Name | Description |
| --- | --- | --- |
| [PID] | principalId | User id |
| Uint64 | uniqueId | |
| Uint32 | order | Rank |
| Uint32 | category | Category |
| Uint32 | score | Score |
| [List]&lt;byte&gt; | groups | Filters |
| Uint64 | param | Additional info |
| [Buffer] | commonData | Additional data |

## RankingChangeAttributesParam ([Structure])
| Type | Name | Description |
| --- | --- | --- |
| Uint8 | modificationFlag | |
| [List]&lt;Uint8&gt; | groups | |
| Uint64 | param | |

## Ranking Mode
| Value | Description |
| --- | --- |
| 0 | Global, only the top 1000 entries be downloaded |
| 1 | Global rankings around own entry |
| 4 | Own ranking only |

[Buffer]: NEX-Common-Types#buffer
[Structure]: NEX-Common-Types#structure
[List]: NEX-Common-Types#list
[PID]: NEX-Common-Types#pid
[DateTime]: NEX-Common-Types#date-time