## [[NEX Protocols]] > [Data Store (0x73)](Data-Store-Protocol) > SMM

This page describes the methods that are only seen in Super Mario Maker. The protocol has been renamed from `DataStoreProtocol` to `DataStoreCustomProtocol`.

| Method ID | Method Name |
| --- | --- |
| 46 | ? |
| 47 | ? |
| 48 | RateCustomRanking |
| 49 | GetCustomRanking |
| 50 | [GetCustomRankingByDataId](#50-getcustomrankingbydataid) |
| 51 | DeleteCustomRanking |
| 52 | [AddToBufferQueue](#52-addtobufferqueue) |
| 53 | [AddToBufferQueues](#53-addtobufferqueues) |
| 54 | [GetBufferQueue](#54-getbufferqueue) |
| 55 | [GetBufferQueues](#55-getbufferqueues) |
| 56 | [ClearBufferQueues](#56-clearbufferqueues) |
| 57 | CompleteAttachFile |
| 58 | CompleteAttachFileV1 |
| 59 | PrepareAttachFile |
| 60 | ConditionalSearchObject |
| 61 | [GetApplicationConfig](#61-getapplicationconfig) |
| 62 | SetApplicationConfig |
| 63 | DeleteApplicationConfig |
| 64 | LatestCourseSearchObject |
| 65 | FollowingsLatestCourseSearchObject |
| 66 | RecommendedCourseSearchObject |
| 67 | ScoreRangeCascadedSearchObject |
| 68 | SuggestedCourseSearchObject |
| 69 | ? |
| 70 | ? |
| 71 | UploadCourseRecord |
| 72 | GetCourseRecord |
| 73 | DeleteCourseRecord |
| 74 | [GetApplicationConfigString](#74-getapplicationconfigstring) |
| 75 | SetApplicationConfigString |
| 76 | [GetDeletionReason](#76-getdeletionreason) |
| 77 | [SetDeletionReason](#77-setdeletionreason) |
| 78 | GetMetasWithCourseRecord |
| 79 | [CheckRateCustomRankingCounter](#79-checkratecustomrankingcounter) |
| 80 | [ResetRateCustomRankingCounter](#80-resetratecustomrankingcounter) |
| 81 | BestScoreRateCourseSearchObject |
| 82 | CTRPickUpCourseSearchObject |
| 83 | SetCachedRanking |
| 84 | DeleteCachedRanking |
| 85 | ChangePlayablePlatform |
| 86 | SearchUnknownPlatformObjects |
| 87 | ReportCourse |

# (50) GetCustomRankingByDataId
## Request
| Type | Description |
| --- | --- |
| [GetCustomRankingByDataIdParam](#getcustomrankingbydataidparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[DataStoreObjectInfo]&gt; | Search result |
| [List]&lt;[Result]&gt; | Results |

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

# (61) GetApplicationConfig
## Request
| Type | Description |
| --- | --- |
| Uint32 | Id |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;Uint32&gt; | Config |

# (74) GetApplicationConfigString
## Request
| Type | Description |
| --- | --- |
| Uint32 | Id |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[String]&gt; | Config |

# (76) GetDeletionReason
## Request
| Type | Description |
| --- | --- |
| [List]&lt;Uint64&gt; | Data ids |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;Uint32&gt; | Deletion reasons |

# (77) SetDeletionReason
## Request
| Type | Description |
| --- | --- |
| [List]&lt;Uint64&gt; | Data ids |
| Uint32 | Deletion reason |

# (79) CheckRateCustomRankingCounter
## Request
| Type | Description |
| --- | --- |
| Uint32 | Unknown |

## Response
| Type | Description |
| --- | --- |
| Bool | Result |

# (80) ResetRateCustomRankingCounter
## Request
| Type | Description |
| --- | --- |
| Uint32 | Unknown |

## Response
This method does not return anything.

# Types
## BufferQueueParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint32 | slot |

## DataStoreObjectInfo ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| Uint32 | Unknown |
| [DataStoreMetaInfo] | Meta info |

## GetCustomRankingByDataIdParam ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| [List]&lt;Uint64&gt; | Data ids |
| Uint8 | Unknown |

[BufferQueueParam]: #bufferqueueparam-structure
[DataStoreObjectInfo]: #datastoreobjectinfo-structure

[DataStoreGetMetaParam]: Data-Store-Protocol#datastoregetmetaparam-structure
[DataStorePreparePostParam]: Data-Store-Protocol#datastorepreparepostparam-structure
[DataStoreCompletePostParam]: Data-Store-Protocol#datastorecompletepostparam-structure
[DataStoreReqGetInfo]: Data-Store-Protocol#datastorereqgetinfo-structure
[DataStoreReqPostInfo]: Data-Store-Protocol#datastorereqpostinfo-structure
[DataStoreMetaInfo]: Data-Store-Protocol#datastoremetainfo-structure

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