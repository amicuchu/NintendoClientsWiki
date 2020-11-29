## [NEX Protocols](NEX-Protocols.md) > [Ranking Protocol (0x70)](Ranking-Protocol.md) > Splatoon 2

This page describes the methods that are only seen in Splatoon 2.

| Method ID | Method Name |
| --- | --- |
| 16 | [UploadLeaguePoint](#16-uploadleaguepoint) |
| 17 | [GetLeagueResult](#17-getleagueresult) |
| 18 | [GetFestivalResult](#18-getfestivalresult) |
| 19 | [UploadFestivalVote](#19-uploadfestivalvote) |
| 20 | [UploadFestivalScore](#20-uploadfestivalscore) |
| 21 | [DeleteFestival](#21-deletefestival) |
| 22 | UploadXPower |
| 23 | GetXPowerRanking |
| 24 | UploadEventMatchResult |
| 25 | GetEventMatchResult |
| 26 | AcquireEventMatchRight |

# (16) UploadLeaguePoint
## Request
| Type | Name |
| --- | --- |
| [LeaguePointInfo] | info |

## Response
This method does not return anything.

# (17) GetLeagueResult
## Request
| Type | Name |
| --- | --- |
| [String] | leagueId |
| Uint64 | tagId |

## Response
| Type | Name |
| --- | --- |
| [LeagueResult] | result |

# (18) GetFestivalResult
## Request
| Type | Name |
| --- | --- |
| Uint32 | festivalId |

## Response
| Type | Name |
| --- | --- |
| [FestivalResult] | result |

# (19) UploadFestivalVote
## Request
| Type | Name |
| --- | --- |
| [FestivalUploadVoteParam] | uploadParam |

## Response
This method does not return anything.

# (20) UploadFestivalScore
## Request
| Type | Name |
| --- | --- |
| [FestivalUploadScoreParam] | uploadParam |

## Response
This method does not return anything.

# (21) DeleteFestival
## Request
| Type | Name |
| --- | --- |
| Uint32 | festivalId |

## Response
This method does not return anything.

# Types
## FestivalResult ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | festivalId |
| Uint32 | numParticipants |
| [List]&lt;Uint32&gt; | teamParticipants |
| [List]&lt;Uint32&gt; | teamScores |
| [DateTime] | updatedTime |

## FestivalUploadScoreParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | uniqueId |
| Uint8 | region |
| Uint32 | festivalId |
| Uint8 | teamId |
| Uint32 | score |
| Uint32 | battleGatheringId |
| Uint32 | battleResult |
| [qBuffer] | applicationBuffer |

## FestivalUploadVoteParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | festivalId |
| Uint8 | themeId |

## LeaguePlayerDetail ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | principalId |
| Sint32 | weaponId |

## LeaguePointInfo ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | tagId |
| Uint8 | regionFlag |
| [String] | leagueId |
| Uint32 | point |
| [Map]&lt;Uint64, [LeaguePlayerDetail]&gt; | tagMembers |
| [qBuffer] | applicationBuffer |

## LeagueResult ([Structure])
| Type | Name |
| --- | --- |
| [LeaguePointInfo] | leaguePointInfo |
| Uint8 | status |
| Uint32 | specificRank |
| Uint8 | rankRatio |
| Uint32 | tagNum |
| Uint32 | matchCount |

[Result]: NEX-Common-Types.md#result
[String]: NEX-Common-Types.md#string
[Buffer]: NEX-Common-Types.md#buffer
[qBuffer]: NEX-Common-Types.md#qbuffer
[List]: NEX-Common-Types.md#list
[Map]: NEX-Common-Types.md#map
[DateTime]: NEX-Common-Types.md#date-time
[Structure]: NEX-Common-Types.md#structure
[Data]: NEX-Common-Types.md#any-data-holder

[RankingScoreData]: #rankingscoredata-structure
[RankingChangeAttributesParam]: #rankingchangeattributesparam-structure
[RankingOrderParam]: #rankingorderparam-structure
[RankingResult]: #rankingresult-structure
[RankingStats]: #rankingstats-structure
[RankingCachedResult]: #rankingcachedresult-structure
[LeaguePointInfo]: #leaguepointinfo-structure
[LeagueResult]: #leagueresult-structure
[FestivalResult]: #festivalresult-structure
[FestivalUploadVoteParam]: #festivaluploadvoteparam-structure
[FestivalUploadScoreParam]: #festivaluploadscoreparam-structure
[RankingRankData]: #rankingrankdata-structure
[LeaguePlayerDetail]: #leagueplayerdetail-structure