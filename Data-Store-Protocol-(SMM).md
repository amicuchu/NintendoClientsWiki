## [[NEX Protocols]] > [Data Store (0x73)](Data-Store-Protocol) > SMM

This page describes the methods that are only seen in Super Mario Maker. The protocol has been renamed from `DataStoreProtocol` to `DataStoreCustomProtocol`.

| Method ID | Method Name |
| --- | --- |
| 46 | [GetMetaByOwnerId](#46-getmetabyownerid) |
| 47 | [CustomSearchObject](#47-customsearchobject) |
| 48 | [RateCustomRanking](#48-ratecustomranking) |
| 49 | [GetCustomRanking](#49-getcustomranking) |
| 50 | [GetCustomRankingByDataId](#50-getcustomrankingbydataid) |
| 51 | [DeleteCustomRanking](#51-deletecustomranking) |
| 52 | [AddToBufferQueue](#52-addtobufferqueue) |
| 53 | [AddToBufferQueues](#53-addtobufferqueues) |
| 54 | [GetBufferQueue](#54-getbufferqueue) |
| 55 | [GetBufferQueues](#55-getbufferqueues) |
| 56 | [ClearBufferQueues](#56-clearbufferqueues) |
| 57 | [CompleteAttachFile](#57-completeattachfile) |
| 58 | [CompleteAttachFileV1](#58-completeattachfilev1) |
| 59 | [PrepareAttachFile](#59-prepareattachfile) |
| 60 | [ConditionalSearchObject](#60-conditionalsearchobject) |
| 61 | [GetApplicationConfig](#61-getapplicationconfig) |
| 62 | [SetApplicationConfig](#62-setapplicationconfig) |
| 63 | [DeleteApplicationConfig](#63-deleteapplicationconfig) |
| 64 | [LatestCourseSearchObject](#64-latestcoursesearchobject) |
| 65 | [FollowingsLatestCourseSearchObject](#65-followingslatestcoursesearchobject) |
| 66 | [RecommendedCourseSearchObject](#66-recommendedcoursesearchobject) |
| 67 | [ScoreRangeCascadedSearchObject](#67-scorerangecascadedsearchobject) |
| 68 | [SuggestedCourseSearchObject](#68-suggestedcoursesearchobject) |
| 69 | [PreparePostObjectWithOwnerIdAndDataId](#69-preparepostobjectwithowneridanddataid) |
| 70 | [CompletePostObjectWithOwnerId](#70-completepostobjectwithownerid) |
| 71 | [UploadCourseRecord](#71-uploadcourserecord) |
| 72 | [GetCourseRecord](#72-getcourserecord) |
| 73 | [DeleteCourseRecord](#73-deletecourserecord) |
| 74 | [GetApplicationConfigString](#74-getapplicationconfigstring) |
| 75 | [SetApplicationConfigString](#75-setapplicationconfigstring) |
| 76 | [GetDeletionReason](#76-getdeletionreason) |
| 77 | [SetDeletionReason](#77-setdeletionreason) |
| 78 | [GetMetasWithCourseRecord](#78-getmetaswithcourserecord) |
| 79 | [CheckRateCustomRankingCounter](#79-checkratecustomrankingcounter) |
| 80 | [ResetRateCustomRankingCounter](#80-resetratecustomrankingcounter) |
| 81 | [BestScoreRateCourseSearchObject](#81-bestscoreratecoursesearchobject) |
| 82 | [CTRPickUpCourseSearchObject](#82-ctrpickupcoursesearchobject) |
| 83 | [SetCachedRanking](#83-setcachedranking) |
| 84 | [DeleteCachedRanking](#84-deletecachedranking) |
| 85 | [ChangePlayablePlatform](#85-changeplayableplatform) |

# (46) GetMetaByOwnerId
## Request
| Type | Name |
| --- | --- |
| [DataStoreGetMetaByOwnerIdParam] | param |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[DataStoreMetaInfo]&gt; | pMetaInfo |
| Bool | pHasNext |

# (47) CustomSearchObject
## Request
| Type | Name |
| --- | --- |
| Uint32 | condition |
| [DataStoreSearchParam] | param |

## Response
| Type | Name |
| --- | --- |
| [DataStoreSearchResult] | pSearchResult |

# (48) RateCustomRanking
## Request
| Type | Name |
| --- | --- |
| [List]&lt;[DataStoreRateCustomRankingParam]&gt; | params |

## Response
This method does not return anything.

# (49) GetCustomRanking
## Request
| Type | Name |
| --- | --- |
| [DataStoreGetCustomRankingParam] | param |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[DataStoreCustomRankingResult]&gt; | pRankingResult |
| [List]&lt;[Result]&gt; | pResults |

# (50) GetCustomRankingByDataId
## Request
| Type | Name |
| --- | --- |
| [DataStoreGetCustomRankingByDataIdParam] | param |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[DataStoreCustomRankingResult]&gt; | pRankingResult |
| [List]&lt;[Result]&gt; | pResults |

# (51) DeleteCustomRanking
## Request
| Type | Name |
| --- | --- |
| [List]&lt;Uint64&gt; | dataIdList |

## Response
This method does not return anything.

# (52) AddToBufferQueue
## Request
| Type | Name |
| --- | --- |
| [BufferQueueParam] | param |
| [qBuffer] | buffer |

## Response
This method does not return anything.

# (53) AddToBufferQueues
## Request
| Type | Name |
| --- | --- |
| [List]&lt;[BufferQueueParam]&gt; | params |
| [List]&lt;[qBuffer]&gt; | buffers |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[Result]&gt; | pResults |

# (54) GetBufferQueue
## Request
| Type | Name |
| --- | --- |
| [BufferQueueParam] | param |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[qBuffer]&gt; | pBufferQueue |

# (55) GetBufferQueues
## Request
| Type | Name |
| --- | --- |
| [List]&lt;[BufferQueueParam]&gt; | params |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[List]&lt;[qBuffer]&gt;&gt; | pBufferQueueLst |
| [List]&lt;[Result]&gt; | pResults |

# (56) ClearBufferQueues
## Request
| Type | Name |
| --- | --- |
| [List]&lt;[BufferQueueParam]&gt; | params |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[Result]&gt; | pResults |

# (57) CompleteAttachFile
## Request
| Type | Name |
| --- | --- |
| [DataStoreCompletePostParam] | param |

## Response
| Type | Name |
| --- | --- |
| [String] | pUrl |

# (58) CompleteAttachFileV1
## Request
| Type | Name |
| --- | --- |
| [DataStoreCompletePostParamV1] | param |

## Response
| Type | Name |
| --- | --- |
| [String] | pUrl |

# (59) PrepareAttachFile
## Request
| Type | Name |
| --- | --- |
| [DataStoreAttachFileParam] | param |

## Response
| Type | Name |
| --- | --- |
| [DataStoreReqPostInfo] | pReqPostInfo |

# (60) ConditionalSearchObject
## Request
| Type | Name |
| --- | --- |
| Uint32 | condition |
| [DataStoreSearchParam] | param |
| [List]&lt;[String]&gt; | extraData |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[DataStoreCustomRankingResult]&gt; | pRankingResults |

# (61) GetApplicationConfig
## Request
| Type | Name |
| --- | --- |
| Uint32 | applicationId |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;Sint32&gt; | config |

# (62) SetApplicationConfig
## Request
| Type | Name |
| --- | --- |
| Uint32 | applicationId |
| Uint32 | key |
| Sint32 | value |

## Response
This method does not return anything.

# (63) DeleteApplicationConfig
## Request
| Type | Name |
| --- | --- |
| Uint32 | applicationId |
| Uint32 | key |

## Response
This method does not return anything.

# (64) LatestCourseSearchObject
## Request
| Type | Name |
| --- | --- |
| [DataStoreSearchParam] | param |
| [List]&lt;[String]&gt; | extraData |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[DataStoreCustomRankingResult]&gt; | pRankingResults |

# (65) FollowingsLatestCourseSearchObject
## Request
| Type | Name |
| --- | --- |
| [DataStoreSearchParam] | param |
| [List]&lt;[String]&gt; | extraData |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[DataStoreCustomRankingResult]&gt; | pRankingResults |

# (66) RecommendedCourseSearchObject
## Request
| Type | Name |
| --- | --- |
| [DataStoreSearchParam] | param |
| [List]&lt;[String]&gt; | extraData |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[DataStoreCustomRankingResult]&gt; | pRankingResults |

# (67) ScoreRangeCascadedSearchObject
## Request
| Type | Name |
| --- | --- |
| [DataStoreSearchParam] | param |
| [List]&lt;[String]&gt; | extraData |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[DataStoreCustomRankingResult]&gt; | pRankingResults |

# (68) SuggestedCourseSearchObject
## Request
| Type | Name |
| --- | --- |
| [DataStoreSearchParam] | param |
| [List]&lt;[String]&gt; | extraData |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[DataStoreCustomRankingResult]&gt; | pRankingResults |

# (69) PreparePostObjectWithOwnerIdAndDataId
## Request
| Type | Name |
| --- | --- |
| Uint32 | ownerId |
| Uint64 | dataId |
| [DataStorePreparePostParam] | param |

## Response
| Type | Name |
| --- | --- |
| [DataStoreReqPostInfo] | pReqPostInfo |

# (70) CompletePostObjectWithOwnerId
## Request
| Type | Name |
| --- | --- |
| Uint32 | ownerId |
| [DataStoreCompletePostParam] | param |

## Response
This method does not return anything.

# (71) UploadCourseRecord
## Request
| Type | Name |
| --- | --- |
| [DataStoreUploadCourseRecordParam] | param |

## Response
This method does not return anything.

# (72) GetCourseRecord
## Request
| Type | Name |
| --- | --- |
| [DataStoreGetCourseRecordParam] | param |

## Response
| Type | Name |
| --- | --- |
| [DataStoreGetCourseRecordResult] | result |

# (73) DeleteCourseRecord
## Request
| Type | Name |
| --- | --- |
| [DataStoreGetCourseRecordParam] | param |

## Response
This method does not return anything.

# (74) GetApplicationConfigString
## Request
| Type | Name |
| --- | --- |
| Uint32 | applicationId |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[String]&gt; | config |

# (75) SetApplicationConfigString
## Request
| Type | Name |
| --- | --- |
| Uint32 | applicationId |
| Uint32 | key |
| [String] | value |

## Response
This method does not return anything.

# (76) GetDeletionReason
## Request
| Type | Name |
| --- | --- |
| [List]&lt;Uint64&gt; | dataIdLst |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;Uint32&gt; | pDeletionReasons |

# (77) SetDeletionReason
## Request
| Type | Name |
| --- | --- |
| [List]&lt;Uint64&gt; | dataIdLst |
| Uint32 | deletionReason |

## Response
This method does not return anything.

# (78) GetMetasWithCourseRecord
## Request
| Type | Name |
| --- | --- |
| [List]&lt;[DataStoreGetCourseRecordParam]&gt; | params |
| [DataStoreGetMetaParam] | metaParam |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[DataStoreMetaInfo]&gt; | pMetaInfo |
| [List]&lt;[DataStoreGetCourseRecordResult]&gt; | pCourseResults |
| [List]&lt;[Result]&gt; | pResults |

# (79) CheckRateCustomRankingCounter
## Request
| Type | Name |
| --- | --- |
| Uint32 | applicationId |

## Response
| Type | Name |
| --- | --- |
| Bool | isBelowThreshold |

# (80) ResetRateCustomRankingCounter
## Request
| Type | Name |
| --- | --- |
| Uint32 | applicationId |

## Response
This method does not return anything.

# (81) BestScoreRateCourseSearchObject
## Request
| Type | Name |
| --- | --- |
| [DataStoreSearchParam] | param |
| [List]&lt;[String]&gt; | extraData |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[DataStoreCustomRankingResult]&gt; | pRankingResults |

# (82) CTRPickUpCourseSearchObject
## Request
| Type | Name |
| --- | --- |
| [DataStoreSearchParam] | param |
| [List]&lt;[String]&gt; | extraData |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[DataStoreCustomRankingResult]&gt; | pRankingResults |

# (83) SetCachedRanking
## Request
| Type | Name |
| --- | --- |
| [String] | rankingType |
| [List]&lt;[String]&gt; | rankingArgs |
| [List]&lt;Uint64&gt; | dataIdLst |

## Response
This method does not return anything.

# (84) DeleteCachedRanking
## Request
| Type | Name |
| --- | --- |
| [String] | rankingType |
| [List]&lt;[String]&gt; | rankingArgs |

## Response
This method does not return anything.

# (85) ChangePlayablePlatform
## Request
| Type | Name |
| --- | --- |
| [List]&lt;[DataStoreChangePlayablePlatformParam]&gt; | params |

## Response
This method does not return anything.

# Types
## BufferQueueParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint32 | slot |

## DataStoreAttachFileParam ([Structure])
| Type | Name |
| --- | --- |
| [DataStorePreparePostParam] | postParam |
| Uint64 | referDataId |
| [String] | contentType |

## DataStoreChangePlayablePlatformParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint32 | playablePlatform |

## DataStoreCustomRankingRatingCondition ([Structure])
| Type | Name |
| --- | --- |
| Sint8 | slot |
| Sint32 | minValue |
| Sint32 | maxValue |
| __dummy_revision | __dummy_revision1 |
| Uint32 | minCount |
| Uint32 | maxCount |

## DataStoreCustomRankingResult ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | order |
| Uint32 | score |
| [DataStoreMetaInfo] | metaInfo |

## DataStoreFileServerObjectInfo ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| [DataStoreReqGetInfo] | getInfo |

## DataStoreGetCourseRecordParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint8 | slot |

## DataStoreGetCourseRecordResult ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint8 | slot |
| Uint32 | firstPid |
| Uint32 | bestPid |
| Sint32 | bestScore |
| [DateTime] | createdTime |
| [DateTime] | updatedTime |

## DataStoreGetCustomRankingByDataIdParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | applicationId |
| [List]&lt;Uint64&gt; | dataIdList |
| Uint8 | resultOption |

## DataStoreGetCustomRankingParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | applicationId |
| [DataStoreCustomRankingRatingCondition] | condition |
| Uint8 | resultOption |
| [ResultRange](NEX-Common-Types#resultrange-structure) | resultRange |

## DataStoreGetMetaByOwnerIdParam ([Structure])
| Type | Name |
| --- | --- |
| [List]&lt;Uint32&gt; | ownerIds |
| [List]&lt;Uint16&gt; | dataTypes |
| Uint8 | resultOption |
| [ResultRange](NEX-Common-Types#resultrange-structure) | resultRange |

## DataStoreRateCustomRankingParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint32 | applicationId |
| Uint32 | score |
| Uint16 | period |

## DataStoreUploadCourseRecordParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint8 | slot |
| Sint32 | score |

[DataStoreGetMetaParam]: Data-Store-Protocol#datastoregetmetaparam-structure
[DataStorePreparePostParam]: Data-Store-Protocol#datastorepreparepostparam-structure
[DataStoreCompletePostParam]: Data-Store-Protocol#datastorecompletepostparam-structure
[DataStoreReqGetInfo]: Data-Store-Protocol#datastorereqgetinfo-structure
[DataStoreReqPostInfo]: Data-Store-Protocol#datastorereqpostinfo-structure
[DataStoreMetaInfo]: Data-Store-Protocol#datastoremetainfo-structure
[DataStoreKeyValue]: Data-Store-Protocol#datastorekeyvalue-structure
[DataStoreSearchParam]: Data-Store-Protocol#datastoresearchparam-structure

[BufferQueueParam]: #bufferqueueparam-structure
[DataStoreAttachFileParam]: #datastoreattachfileparam-structure
[DataStoreChangePlayablePlatformParam]: #datastorechangeplayableplatformparam-structure
[DataStoreCustomRankingRatingCondition]: #datastorecustomrankingratingcondition-structure
[DataStoreCustomRankingResult]: #datastorecustomrankingresult-structure
[DataStoreFileServerObjectInfo]: #datastorefileserverobjectinfo-structure
[DataStoreGetCourseRecordParam]: #datastoregetcourserecordparam-structure
[DataStoreGetCourseRecordResult]: #datastoregetcourserecordresult-structure
[DataStoreGetCustomRankingByDataIdParam]: #datastoregetcustomrankingbydataidparam-structure
[DataStoreGetCustomRankingParam]: #datastoregetcustomrankingparam-structure
[DataStoreGetMetaByOwnerIdParam]: #datastoregetmetabyowneridparam-structure
[DataStoreRateCustomRankingParam]: #datastoreratecustomrankingparam-structure
[DataStoreUploadCourseRecordParam]: #datastoreuploadcourserecordparam-structure

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
