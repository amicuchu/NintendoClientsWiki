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
## DataStorePrepareGetParamV1 ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | dataId |
| Uint32 | lockId |

## DataStorePrepareGetParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint32 | lockId |
| [DataStorePersistenceTarget] | persistenceTarget |
| Uint64 | accessPassword |
| [List]&lt;[String]&gt; | extraData |

## DataStoreReqGetInfoV1 ([Structure])
| Type | Name |
| --- | --- |
| [String] | url |
| [List]&lt;[DataStoreKeyValue]&gt; | requestHeaders |
| Uint32 | size |
| [Buffer] | rootCaCert |

## DataStoreReqGetInfo ([Structure])
| Type | Name |
| --- | --- |
| [String] | url |
| [List]&lt;[DataStoreKeyValue]&gt; | requestHeaders |
| Uint32 | size |
| [Buffer] | rootCaCert |
| Uint64 | dataId |

## DataStoreReqGetAdditionalMeta ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | ownerId |
| Uint16 | dataType |
| Uint16 | version |
| [qBuffer] | metaBinary |

## DataStorePreparePostParamV1 ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | size |
| [String] | name |
| Uint16 | dataType |
| [qBuffer] | metaBinary |
| [DataStorePermission] | permission |
| [DataStorePermission] | delPermission |
| Uint32 | flag |
| Uint16 | period |
| Uint32 | referDataId |
| [List]&lt;[String]&gt; | tags |
| [List]&lt;[DataStoreRatingInitParamWithSlot]&gt; | ratingInitParams |

## DataStorePreparePostParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | size |
| [String] | name |
| Uint16 | dataType |
| [qBuffer] | metaBinary |
| [DataStorePermission] | permission |
| [DataStorePermission] | delPermission |
| Uint32 | flag |
| Uint16 | period |
| Uint32 | referDataId |
| [List]&lt;[String]&gt; | tags |
| [List]&lt;[DataStoreRatingInitParamWithSlot]&gt; | ratingInitParams |
| [DataStorePersistenceInitParam] | persistenceInitParam |
| [List]&lt;[String]&gt; | extraData |

## DataStoreReqPostInfoV1 ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | dataId |
| [String] | url |
| [List]&lt;[DataStoreKeyValue]&gt; | requestHeaders |
| [List]&lt;[DataStoreKeyValue]&gt; | formFields |
| [Buffer] | rootCaCert |

## DataStoreReqPostInfo ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| [String] | url |
| [List]&lt;[DataStoreKeyValue]&gt; | requestHeaders |
| [List]&lt;[DataStoreKeyValue]&gt; | formFields |
| [Buffer] | rootCaCert |

## DataStoreCompletePostParamV1 ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | dataId |
| Bool | isSuccess |

## DataStoreCompletePostParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Bool | isSuccess |

## DataStoreDeleteParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint64 | updatePassword |

## DataStoreChangeMetaParamV1 ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint32 | modifiesFlag |
| [String] | name |
| [DataStorePermission] | permission |
| [DataStorePermission] | delPermission |
| Uint16 | period |
| [qBuffer] | metaBinary |
| [List]&lt;[String]&gt; | tags |
| Uint64 | updatePassword |

## DataStoreChangeMetaParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint32 | modifiesFlag |
| [String] | name |
| [DataStorePermission] | permission |
| [DataStorePermission] | delPermission |
| Uint16 | period |
| [qBuffer] | metaBinary |
| [List]&lt;[String]&gt; | tags |
| Uint64 | updatePassword |
| Uint32 | referredCnt |
| Uint16 | dataType |
| Uint8 | status |
| [DataStoreChangeMetaCompareParam] | compareParam |

## DataStoreGetMetaParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| [DataStorePersistenceTarget] | persistenceTarget |
| Uint8 | resultOption |
| Uint64 | accessPassword |

## DataStoreRatingInfo ([Structure])
| Type | Name |
| --- | --- |
| Sint64 | totalValue |
| Uint32 | count |
| Sint64 | initialValue |

## DataStoreRatingInfoWithSlot ([Structure])
| Type | Name |
| --- | --- |
| Sint8 | slot |
| [DataStoreRatingInfo] | rating |

## DataStoreMetaInfo ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint32 | ownerId |
| Uint32 | size |
| [String] | name |
| Uint16 | dataType |
| [qBuffer] | metaBinary |
| [DataStorePermission] | permission |
| [DataStorePermission] | delPermission |
| [DateTime] | createdTime |
| [DateTime] | updatedTime |
| Uint16 | period |
| Uint8 | status |
| Uint32 | referredCnt |
| Uint32 | referDataId |
| Uint32 | flag |
| [DateTime] | referredTime |
| [DateTime] | expireTime |
| [List]&lt;[String]&gt; | tags |
| [List]&lt;[DataStoreRatingInfoWithSlot]&gt; | ratings |

## DataStorePrepareUpdateParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint32 | size |
| Uint64 | updatePassword |
| [List]&lt;[String]&gt; | extraData |

## DataStoreReqUpdateInfo ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | version |
| [String] | url |
| [List]&lt;[DataStoreKeyValue]&gt; | requestHeaders |
| [List]&lt;[DataStoreKeyValue]&gt; | formFields |
| [Buffer] | rootCaCert |

## DataStoreCompleteUpdateParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint32 | version |
| Bool | isSuccess |

## DataStoreSearchParam ([Structure])
| Type | Name |
| --- | --- |
| Uint8 | searchTarget |
| [List]&lt;Uint32&gt; | ownerIds |
| Uint8 | ownerType |
| [List]&lt;Uint32&gt; | destinationIds |
| Uint16 | dataType |
| [DateTime] | createdAfter |
| [DateTime] | createdBefore |
| [DateTime] | updatedAfter |
| [DateTime] | updatedBefore |
| Uint32 | referDataId |
| [List]&lt;[String]&gt; | tags |
| Uint8 | resultOrderColumn |
| Uint8 | resultOrder |
| [ResultRange](NEX-Common-Types#resultrange-structure) | resultRange |
| Uint8 | resultOption |
| Uint32 | minimalRatingFrequency |
| __dummy_revision | __dummy_revision1 |
| Bool | useCache |

## DataStoreSearchResult ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | totalCount |
| [List]&lt;[DataStoreMetaInfo]&gt; | result |
| Uint8 | totalCountType |

## DataStoreGetNotificationUrlParam ([Structure])
| Type | Name |
| --- | --- |
| [String] | previousUrl |

## DataStoreReqGetNotificationUrlInfo ([Structure])
| Type | Name |
| --- | --- |
| [String] | url |
| [String] | key |
| [String] | query |
| [Buffer] | rootCaCert |

## DataStoreGetNewArrivedNotificationsParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | lastNotificationId |
| Uint16 | limit |

## DataStoreNotificationV1 ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | notificationId |
| Uint32 | dataId |

## DataStoreNotification ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | notificationId |
| Uint64 | dataId |

## DataStoreRateObjectParam ([Structure])
| Type | Name |
| --- | --- |
| Sint32 | ratingValue |
| Uint64 | accessPassword |

## DataStoreRatingTarget ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Sint8 | slot |

## DataStoreGetSpecificMetaParamV1 ([Structure])
| Type | Name |
| --- | --- |
| [List]&lt;Uint32&gt; | dataIds |

## DataStoreGetSpecificMetaParam ([Structure])
| Type | Name |
| --- | --- |
| [List]&lt;Uint64&gt; | dataIds |

## DataStoreSpecificMetaInfoV1 ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | dataId |
| Uint32 | ownerId |
| Uint32 | size |
| Uint16 | dataType |
| Uint16 | version |

## DataStoreSpecificMetaInfo ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint32 | ownerId |
| Uint32 | size |
| Uint16 | dataType |
| Uint32 | version |

## DataStoreTouchObjectParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint32 | lockId |
| Uint64 | accessPassword |

## DataStoreRatingLog ([Structure])
| Type | Name |
| --- | --- |
| Bool | isRated |
| Uint32 | pid |
| Sint32 | ratingValue |
| [DateTime] | lockExpirationTime |

## DataStorePersistenceInfo ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | ownerId |
| Uint16 | persistenceSlotId |
| Uint64 | dataId |

## DataStorePasswordInfo ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint64 | accessPassword |
| Uint64 | updatePassword |

## DataStoreFileServerObjectInfo ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| [DataStoreReqGetInfo] | getInfo |

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

## DataStoreGetCustomRankingParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | applicationId |
| [DataStoreCustomRankingRatingCondition] | condition |
| Uint8 | resultOption |
| [ResultRange](NEX-Common-Types#resultrange-structure) | resultRange |

## DataStoreGetCustomRankingByDataIdParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | applicationId |
| [List]&lt;Uint64&gt; | dataIdList |
| Uint8 | resultOption |

## DataStoreCustomRankingResult ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | order |
| Uint32 | score |
| [DataStoreMetaInfo] | metaInfo |

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

## DataStoreUploadCourseRecordParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint8 | slot |
| Sint32 | score |

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

## DataStoreChangePlayablePlatformParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint32 | playablePlatform |

## DataStorePersistenceTarget ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | ownerId |
| Uint16 | persistenceSlotId |

## DataStoreKeyValue ([Structure])
| Type | Name |
| --- | --- |
| [String] | key |
| [String] | value |

## DataStorePermission ([Structure])
| Type | Name |
| --- | --- |
| Uint8 | permission |
| [List]&lt;Uint32&gt; | recipientIds |

## DataStoreRatingInitParamWithSlot ([Structure])
| Type | Name |
| --- | --- |
| Sint8 | slot |
| [DataStoreRatingInitParam] | param |

## DataStorePersistenceInitParam ([Structure])
| Type | Name |
| --- | --- |
| Uint16 | persistenceSlotId |
| Bool | deleteLastObject |

## DataStoreChangeMetaCompareParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | comparisonFlag |
| [String] | name |
| [DataStorePermission] | permission |
| [DataStorePermission] | delPermission |
| Uint16 | period |
| [qBuffer] | metaBinary |
| [List]&lt;[String]&gt; | tags |
| Uint32 | referredCnt |
| Uint16 | dataType |
| Uint8 | status |

## DataStoreCustomRankingRatingCondition ([Structure])
| Type | Name |
| --- | --- |
| Sint8 | slot |
| Sint32 | minValue |
| Sint32 | maxValue |
| __dummy_revision | __dummy_revision1 |
| Uint32 | minCount |
| Uint32 | maxCount |

## DataStoreRatingInitParam ([Structure])
| Type | Name |
| --- | --- |
| Uint8 | flag |
| Uint8 | internalFlag |
| Uint8 | lockType |
| Sint64 | initialValue |
| Sint32 | rangeMin |
| Sint32 | rangeMax |
| Sint8 | periodHour |
| Sint16 | periodDuration |