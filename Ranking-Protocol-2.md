## [[NEX Protocols]] > Ranking 2 (0x7A)

| Method ID | Method Name |
| --- | --- |
| 1 | [PutScore](#1-putscore) |
| 2 | [GetCommonData](#2-getcommondata) |
| 3 | [PutCommonData](#3-putcommondata) |
| 4 | [DeleteCommonData](#4-deletecommondata) |
| 5 | [GetRanking](#5-getranking) |
| 6 | [GetRankingByPrincipalId](#6-getrankingbyprincipalid) |
| 7 | [GetCategorySetting](#7-getcategorysetting) |
| 8 | [GetRankingChart](#8-getrankingchart) |
| 9 | [GetRankingCharts](#9-getrankingcharts) |
| 10 | [GetEstimateScoreRank](#10-getestimatescorerank) |

# (1) PutScore
## Request
| Type | Name |
| --- | --- |
| [List]&lt;[Ranking2ScoreData]&gt; | scoreDataList |
| Uint64 | nexUniqueId |

## Response
This method does not return anything.

# (2) GetCommonData
## Request
| Type | Name |
| --- | --- |
| Uint32 | optionFlags |
| [PID] | principalId |
| Uint64 | nexUniqueId |

## Response
| Type | Name |
| --- | --- |
| [Ranking2CommonData] | commonData |

# (3) PutCommonData
## Request
| Type | Name |
| --- | --- |
| [Ranking2CommonData] | commonData |
| Uint64 | nexUniqueId |

## Response
This method does not return anything.

# (4) DeleteCommonData
## Request
| Type | Name |
| --- | --- |
| Uint64 | nexUniqueId |

## Response
This method does not return anything.

# (5) GetRanking
## Request
| Type | Name |
| --- | --- |
| [Ranking2GetParam] | getParam |

## Response
| Type | Name |
| --- | --- |
| [Ranking2Info] | rankingInfo |

# (6) GetRankingByPrincipalId
## Request
| Type | Name |
| --- | --- |
| [Ranking2GetByListParam] | getParam |
| [List]&lt;[PID]&gt; | principalIdList |

## Response
| Type | Name |
| --- | --- |
| [Ranking2Info] | rankingInfo |

# (7) GetCategorySetting
## Request
| Type | Name |
| --- | --- |
| Uint32 | category |

## Response
| Type | Name |
| --- | --- |
| [Ranking2CategorySetting] | categorySetting |

# (8) GetRankingChart
## Request
| Type | Name |
| --- | --- |
| [Ranking2ChartInfoInput] | info |

## Response
| Type | Name |
| --- | --- |
| [Ranking2ChartInfo] | chart |

# (9) GetRankingCharts
## Request
| Type | Name |
| --- | --- |
| [List]&lt;[Ranking2ChartInfoInput]&gt; | infoArray |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[Ranking2ChartInfo]&gt; | chartArray |

# (10) GetEstimateScoreRank
## Request
| Type | Name |
| --- | --- |
| [Ranking2EstimateScoreRankInput] | input |

## Response
| Type | Name |
| --- | --- |
| [Ranking2EstimateScoreRankOutput] | output |

# Types
## Ranking2CommonData ([Structure])
| Type | Name |
| --- | --- |
| [String] | userName |
| [qBuffer] | mii |
| [qBuffer] | binaryData |

## Ranking2ScoreData ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | misc |
| Uint32 | category |
| Uint32 | score |

## Ranking2GetParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | nexUniqueId |
| [PID] | principalId |
| Uint32 | category |
| Uint32 | offset |
| Uint32 | length |
| Uint32 | sortFlags |
| Uint32 | optionFlags |
| Uint8 | mode |
| Uint8 | numSeasonsToGoBack |

## Ranking2GetByListParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | category |
| Uint32 | offset |
| Uint32 | length |
| Uint32 | sortFlags |
| Uint32 | optionFlags |
| Uint8 | numSeasonsToGoBack |

## Ranking2Info ([Structure])
| Type | Name |
| --- | --- |
| [List]&lt;[Ranking2RankData]&gt; | rankDataList |
| Uint32 | lowestRank |
| Uint32 | numRankedIn |
| Sint32 | season |

## Ranking2CategorySetting ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | minScore |
| Uint32 | maxScore |
| Uint32 | lowestRank |
| Uint16 | resetMonth |
| Uint8 | resetDay |
| Uint8 | resetHour |
| Uint8 | resetMode |
| Uint8 | maxSeasonsToGoBack |
| Bool | scoreOrder |

## Ranking2ChartInfoInput ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | chartIndex |
| Uint8 | numSeasonsToGoBack |

## Ranking2ChartInfo ([Structure])
| Type | Name |
| --- | --- |
| [DateTime] | createTime |
| Uint32 | index |
| Uint32 | category |
| Sint32 | season |
| Uint8 | binsSize |
| Uint8 | samplingRate |
| Bool | scoreOrder |
| Uint32 | estimateLength |
| Uint32 | estimateHighestScore |
| Uint32 | estimateLowestScore |
| Uint32 | estimateMedianScore |
| Double | estimateAverageScore |
| Uint32 | highestBinsScore |
| Uint32 | lowestBinsScore |
| Uint32 | binsWidth |
| Uint32 | attribute1 |
| Uint32 | attribute2 |
| [List]&lt;Uint32&gt; | quantities |

## Ranking2EstimateScoreRankInput ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | category |
| Uint8 | numSeasonsToGoBack |
| Uint32 | score |

## Ranking2EstimateScoreRankOutput ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | rank |
| Uint32 | length |
| Uint32 | score |
| Uint32 | category |
| Sint32 | season |
| Uint8 | samplingRate |

## Ranking2RankData ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | misc |
| Uint64 | nexUniqueId |
| [PID] | principalId |
| Uint32 | rank |
| Uint32 | score |
| [Ranking2CommonData] | commonData |

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

[Ranking2ScoreData]: #ranking2scoredata-structure
[Ranking2CommonData]: #ranking2commondata-structure
[Ranking2GetParam]: #ranking2getparam-structure
[Ranking2Info]: #ranking2info-structure
[Ranking2GetByListParam]: #ranking2getbylistparam-structure
[Ranking2CategorySetting]: #ranking2categorysetting-structure
[Ranking2ChartInfoInput]: #ranking2chartinfoinput-structure
[Ranking2ChartInfo]: #ranking2chartinfo-structure
[Ranking2EstimateScoreRankInput]: #ranking2estimatescorerankinput-structure
[Ranking2EstimateScoreRankOutput]: #ranking2estimatescorerankoutput-structure
[Ranking2RankData]: #ranking2rankdata-structure
