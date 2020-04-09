## [[NEX Protocols]] > [Data Store (0x73)](Data-Store-Protocol) > Splatoon 2

This page describes the methods that are only seen in Splatoon 2.

| Method ID | Method Name |
| --- | --- |
| 47 | [CoconutRegisterMeta](#47-coconutregistermeta) |
| 48 | [CoconutRatePost](#48-coconutratepost) |
| 49 | [CoconutGetObjectInfos](#49-coconutgetobjectinfos) |
| 50 | [CoconutReportViolation](#50-coconutreportviolation) |
| 51 | [UploadRegularMatchResult](#51-uploadregularmatchresult) |
| 52 | [UploadGachiMatchResult](#52-uploadgachimatchresult) |
| 53 | [UploadLeagueMatchResult](#53-uploadleaguematchresult) |
| 54 | [UploadFesMatchResult](#54-uploadfesmatchresult) |
| 55 | [GetOrderedGear](#55-getorderedgear) |
| 56 | [PurchaseGear](#56-purchasegear) |
| 57 | [UploadTimeAttack](#57-uploadtimeattack) |
| 58 | [CoconutRegisterMetaByParam](#58-coconutregistermetabyparam) |
| 59 | [UploadFesMatchResultV2](#59-uploadfesmatchresultv2) |

# (47) CoconutRegisterMeta
## Request
| Type | Name |
| --- | --- |
| [CoconutMeta] | meta |
| [String] | url |

## Response
This method does not return anything.

# (48) CoconutRatePost
## Request
| Type | Name |
| --- | --- |
| Uint64 | dataId |

## Response
This method does not return anything.

# (49) CoconutGetObjectInfos
## Request
| Type | Name |
| --- | --- |
| [CoconutGetParam] | param |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[CoconutGetInfo]&gt; | pInfos |
| [List]&lt;[Result]&gt; | pResults |

# (50) CoconutReportViolation
## Request
| Type | Name |
| --- | --- |
| [CoconutViolation] | violation |

## Response
This method does not return anything.

# (51) UploadRegularMatchResult
## Request
| Type | Name |
| --- | --- |
| [CalicoRegularStats] | stats |

## Response
This method does not return anything.

# (52) UploadGachiMatchResult
## Request
| Type | Name |
| --- | --- |
| [CalicoGachiStats] | stats |

## Response
This method does not return anything.

# (53) UploadLeagueMatchResult
## Request
| Type | Name |
| --- | --- |
| [CalicoLeagueStats] | stats |

## Response
This method does not return anything.

# (54) UploadFesMatchResult
## Request
| Type | Name |
| --- | --- |
| [CalicoFesStats] | stats |

## Response
This method does not return anything.

# (55) GetOrderedGear
## Request
This method does not take any parameters.

## Response
| Type | Name |
| --- | --- |
| [OrderedInfo] | info |

# (56) PurchaseGear
## Request
| Type | Name |
| --- | --- |
| [OrderedInfo] | info |

## Response
This method does not return anything.

# (57) UploadTimeAttack
## Request
| Type | Name |
| --- | --- |
| [TimeAttackInfo] | info |

## Response
This method does not return anything.

# (58) CoconutRegisterMetaByParam
## Request
| Type | Name |
| --- | --- |
| [CoconutMeta] | meta |
| [String] | snsName |
| [String] | postId |

## Response
This method does not return anything.

# (59) UploadFesMatchResultV2
## Request
| Type | Name |
| --- | --- |
| [CalicoFesStatsV2] | stats |

## Response
This method does not return anything.

# Types
## CoconutMeta ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint64 | tweetId |
| Uint8 | region |
| Uint8 | postType |
| Uint8 | themeId |
| Uint32 | festivalId |
| [String] | language |
| [qBuffer] | binaryData |

## CoconutGetParam ([Structure])
| Type | Name |
| --- | --- |
| [List]&lt;Uint64&gt; | uniqueIds |
| Uint8 | getType |
| Uint8 | region |
| Uint32 | festivalId |

## CoconutGetInfo ([Structure])
| Type | Name |
| --- | --- |
| [DataStoreReqGetInfo] | info |
| [CoconutMeta] | meta |

## CoconutViolation ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| [String] | categoryCode |
| [String] | reason |

## CalicoRegularStats ([Structure])
| Type | Name |
| --- | --- |
| Sint32 | myTeamPercentage |
| Sint32 | otherTeamPercentage |
| Sint32 | winMeter |

## CalicoGachiStats ([Structure])
| Type | Name |
| --- | --- |
| Sint32 | elapsedTime |
| Sint8 | myTeamCount |
| Sint8 | otherTeamCount |
| Sint32 | udemae |
| Sint32 | estimateGachiPower |

## CalicoLeagueStats ([Structure])
| Type | Name |
| --- | --- |
| [String] | leagueId |
| Uint64 | tagId |
| Sint32 | leaguePoint |
| Sint32 | maxLeaguePoint |
| Sint32 | myEstimateLeaguePoint |
| Sint32 | otherEstimateLeaguePoint |

## CalicoFesStats ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | fesId |
| Uint8 | themeId |
| Sint32 | fesGrade |
| Sint32 | fesPoint |
| Uint32 | fesPower |
| Uint32 | maxFesPower |
| Sint32 | myEstimateFesPower |
| Sint32 | otherEstimateFesPower |

## OrderedInfo ([Structure])
| Type | Name |
| --- | --- |
| Sint32 | gearKind |
| Sint32 | gearId |
| Sint32 | skillId |
| Sint32 | price |

## TimeAttackInfo ([Structure])
| Type | Name |
| --- | --- |
| [Map]&lt;Sint32, [StageTimeAttackInfo]&gt; | stageInfos |

## CalicoFesStatsV2 ([Structure])
| Type | Name |
| --- | --- |
| Uint8 | otherThemeId |

## StageTimeAttackInfo ([Structure])
| Type | Name |
| --- | --- |
| [Map]&lt;Sint32, [StageTimeAttackWeapon]&gt; | clearWeapons |

## StageTimeAttackWeapon ([Structure])
| Type | Name |
| --- | --- |
| Sint32 | weaponLevel |
| Sint32 | clearTime |

[Result]: NEX-Common-Types#result
[String]: NEX-Common-Types#string
[Buffer]: NEX-Common-Types#buffer
[qBuffer]: NEX-Common-Types#qbuffer
[List]: NEX-Common-Types#list
[Map]: NEX-Common-Types#map
[DateTime]: NEX-Common-Types#date-time
[Structure]: NEX-Common-Types#structure
[Data]: NEX-Common-Types#any-data-holder

[CoconutMeta]: #coconutmeta-structure
[CoconutGetParam]: #coconutgetparam-structure
[CoconutGetInfo]: #coconutgetinfo-structure
[CoconutViolation]: #coconutviolation-structure
[CalicoRegularStats]: #calicoregularstats-structure
[CalicoGachiStats]: #calicogachistats-structure
[CalicoLeagueStats]: #calicoleaguestats-structure
[CalicoFesStats]: #calicofesstats-structure
[OrderedInfo]: #orderedinfo-structure
[TimeAttackInfo]: #timeattackinfo-structure
[CalicoFesStatsV2]: #calicofesstatsv2-structure
[StageTimeAttackInfo]: #stagetimeattackinfo-structure
[StageTimeAttackWeapon]: #stagetimeattackweapon-structure

[DataStoreReqGetInfo]: Data-Store-Protocol#datastorereqgetinfo-structure