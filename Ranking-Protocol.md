## [[NEX Protocols]] > Ranking (0x70)

| Method ID | Method Name |
| --- | --- |
| 1 | UploadScore |
| 2 | DeleteScore |
| 3 | [DeleteAllScores](#3-deleteallscores) |
| 4 | [UploadCommonData](#4-uploadcommondata) |
| 5 | DeleteCommonData |
| 6 | [GetCommonData](#6-getcommondata) |
| 7 | ChangeAttributes |
| 8 | ChangeAllAttributes |
| 9 | [GetRanking](#9-getranking) |
| 10 | GetApproxOrder |
| 11 | GetStats |
| 12 | GetRankingByPIDList |
| 13 | GetRankingByUniqueIdList |
| 14 | GetCachedTopXRanking |
| 15 | GetCachedTopXRankings |

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

# (6) GetCommonData
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint64 | uniqueId | Data id |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [Buffer] | commonData | Data |

# (9) GetRanking
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint8 | rankingMode | Mode |
| Uint32 | category | Category (game-specific) |
| RankingOrderParam | orderParam | A bunch of parameters |
| Uint64 | uniqueId | |
| Uint32 | principalId | |

### Ranking Mode
| Value | Description |
| --- | --- |
| 0 | Global, only the top 1000 rankings be downloaded |
| 1 | Global rankings around own ranking |
| 4 | Own ranking only

### Ranking Order Param ([Structure])
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

## Response
| Type | Name | Description |
| --- | --- | --- |
| RankingResult | pResult | The result |

### Ranking Result ([Structure])
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;RankingRankData&gt; | rankDataList | Rankings |
| Uint32 | totalCount | Total number of ranking entries on the server |
| [DateTime] | sinceTime | |

#### Ranking Rank Data ([Structure])
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | principalId | User pid |
| Uint64 | uniqueId | |
| Uint32 | order | Rank |
| Uint32 | category | Category |
| Uint32 | score | Score |
| [List]&lt;byte&gt; | groups | Filters |
| Uint64 | param | Additional info |
| [Buffer] | commonData | Additional data |

[Buffer]: NEX-Common-Types#buffer
[Structure]: NEX-Common-Types#structure
[List]: NEX-Common-Types#list
[DateTime]: NEX-Common-Types#date-time