## [[NEX Protocols]] > Ranking (0x70)

| Method ID | Method Name |
| --- | --- |
| 1 | UploadScore |
| 2 | DeleteScore |
| 3 | DeleteAllScores |
| 4 | UploadCommonData |
| 5 | DeleteCommonData |
| 6 | GetCommonData |
| 7 | ChangeAttributes |
| 8 | ChangeAllAttributes |
| 9 | GetRanking |
| 10 | GetApproxOrder |
| 11 | GetStats |
| 12 | GetRankingByPIDList |
| 13 | GetRankingByUniqueIdList |
| 14 | GetCachedTopXRanking |
| 15 | GetCachedTopXRankings |

# (1) UploadScore

# (2) DeleteScore

# (3) DeleteAllScores
## Request
| Type | Description |
| --- | --- |
| Uint64 | Unknown |

## Response
This method does not return anything.

# (4) UploadCommonData
## Request
| Type | Description |
| --- | --- |
| [Buffer] | Data |
| Uint64 | Data id |

## Response
This method does not return anything.

# (5) DeleteCommonData

# (6) GetCommonData
## Request
| Type | Description |
| --- | --- |
| Uint64 | Data id |

## Response
| Type | Description |
| --- | --- |
| [Buffer] | Data |

# (7) ChangeAttributes

# (8) ChangeAllAttributes

# (9) GetRanking

## Request
| Type | Description |
| --- | --- |
| Uint8 | Mode |
| Uint32 | Category (probably game-specific) |
| RankingOrderParam | A bunch of parameters |
| Uint64 | Unknown |
| Uint32 | Unknown |

### Ranking Mode
| Value | Description |
| --- | --- |
| 0 | Global, only the top 1000 rankings be downloaded |
| 1 | Global rankings around own ranking |
| 4 | Own ranking only

### Ranking Order Param ([Structure])
| Type | Description |
| --- | --- |
| Uint8 | Rank calculation |
| Uint8 | Filter index |
| Uint8 | Filter number |
| Uint8 | Time scope |
| Uint32 | Base rank (0 is world record) |
| Uint8 | Desired number of rankings |

#### Ranking Calculation
| Value | Description |
| --- | --- |
| 0 | Standard ranking (1224) |
| 1 | Ordinal ranking (1234) |

## Response
| Type | Description |
| --- | --- |
| RankingResult | The result |

### Ranking Result ([Structure])
| Type | Description |
| --- | --- |
| [List]&lt;RankingRankData&gt; | Rankings |
| Uint32 | Total number of ranking entries on the server |
| [DateTime] | Unknown date time |

#### Ranking Rank Data ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | User pid |
| Uint64 | Unknown |
| Uint32 | Rank |
| Uint32 | Category |
| Uint32 | Score |
| [Buffer] | Data 1 |
| Uint64 | Additional info |
| [Buffer] | Data 2 |

# (10) GetApproxOrder

# (11) GetStats

# (12) GetRankingByPIDList

# (13) GetRankingByUniqueIdList

# (14) GetCachedTopXRanking

# (15) GetCachedTopXRankings

[Buffer]: NEX-Common-Types#buffer
[Structure]: NEX-Common-Types#structure
[List]: NEX-Common-Types#list
[DateTime]: NEX-Common-Types#date-time