## [[NEX Protocols]] > [Data Store (0x73)](Data-Store-Protocol) > SMO

This page describes the methods that are only seen in Super Mario Odyssey.

| Method ID | Method Name |
| --- | --- |
| 47 | [AddToBufferQueue](#47-addtobufferqueue) |
| 48 | [AddToBufferQueues](#48-addtobufferqueues) |
| 49 | [GetBufferQueue](#49-getbufferqueue) |
| 50 | [GetBufferQueues](#50-getbufferqueues) |
| 51 | [ClearBufferQueues](#51-clearbufferqueues) |
| 52 | [SearchBalloon](#52-searchballoon) |
| 53 | [FetchMyInfos](#53-fetchmyinfos) |

# (47) AddToBufferQueue
## Request
| Type | Name |
| --- | --- |
| [BufferQueueParam] | param |
| [qBuffer] | buffer |

## Response
This method does not return anything.

# (48) AddToBufferQueues
## Request
| Type | Name |
| --- | --- |
| [List]&lt;[BufferQueueParam]&gt; | params |
| [List]&lt;[qBuffer]&gt; | buffers |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[Result]&gt; | pResults |

# (49) GetBufferQueue
## Request
| Type | Name |
| --- | --- |
| [BufferQueueParam] | param |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[qBuffer]&gt; | pBufferQueue |

# (50) GetBufferQueues
## Request
| Type | Name |
| --- | --- |
| [List]&lt;[BufferQueueParam]&gt; | params |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[List]&lt;[qBuffer]&gt;&gt; | pBufferQueueLst |
| [List]&lt;[Result]&gt; | pResults |

# (51) ClearBufferQueues
## Request
| Type | Name |
| --- | --- |
| [List]&lt;[BufferQueueParam]&gt; | params |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[Result]&gt; | pResults |

# (52) SearchBalloon
## Request
| Type | Name |
| --- | --- |
| [DataStoreSearchBalloonParam] | param |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[DataStoreSearchBalloonResultSet]&gt; | pResults |

# (53) FetchMyInfos
## Request
| Type | Name |
| --- | --- |
| [DataStoreFetchMyInfosParam] | patam |

## Response
| Type | Name |
| --- | --- |
| [DataStoreFetchMyInfosResult] | pResult |

# Types
## BufferQueueParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint32 | slot |

## DataStoreSearchBalloonParam ([Structure])
| Type | Name |
| --- | --- |
| Uint16 | dataType |
| Uint8 | userRank |
| Uint8 | resultSetCount |

## DataStoreSearchBalloonResultSet ([Structure])
| Type | Name |
| --- | --- |
| [List]&lt;[DataStoreSearchBalloonResult]&gt; | balloons |

## DataStoreFetchMyInfosParam ([Structure])
| Type | Name |
| --- | --- |
| [List]&lt;Uint16&gt; | balloonDataTypes |
| Uint16 | additionalOperation |

## DataStoreFetchMyInfosResult ([Structure])
| Type | Name |
| --- | --- |
| [List]&lt;[DataStoreFetchMyInfosBalloonResult]&gt; | balloons |
| [DataStoreFetchMyInfosAchievementResult] | achievement |

## DataStoreSearchBalloonResult ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| [PID] | ownerId |
| Uint32 | size |
| [String] | name |
| Uint16 | dataType |
| [qBuffer] | metaBinary |
| [DateTime] | createdTime |
| [DateTime] | updatedTime |
| Uint64 | ownerDataId |
| [String] | ownerName |
| Bool | isFriendBalloon |
| [Map]&lt;Sint8, [DataStoreRatingInfo]&gt; | ratings |
| [Map]&lt;Sint8, [DataStoreRatingInfo]&gt; | ownerRatings |

## DataStoreFetchMyInfosBalloonResult ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint16 | dataType |
| [qBuffer] | metaBinary |
| [DateTime] | createdTime |
| [DateTime] | updatedTime |
| Bool | isCleared |
| [Map]&lt;Sint8, [DataStoreRatingInfo]&gt; | ratings |
| [Map]&lt;Sint8, [List]&lt;[qBuffer]&gt;&gt; | buffers |

## DataStoreFetchMyInfosAchievementResult ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint16 | dataType |
| [qBuffer] | metaBinary |
| [DateTime] | createdTime |
| [Map]&lt;Sint8, [DataStoreRatingInfo]&gt; | ratings |
| [Map]&lt;Sint8, [List]&lt;[qBuffer]&gt;&gt; | buffers |

[BufferQueueParam]: #bufferqueueparam-structure
[DataStoreSearchBalloonParam]: #datastoresearchballoonparam-structure
[DataStoreSearchBalloonResultSet]: #datastoresearchballoonresultset-structure
[DataStoreFetchMyInfosParam]: #datastorefetchmyinfosparam-structure
[DataStoreFetchMyInfosResult]: #datastorefetchmyinfosresult-structure
[DataStoreSearchBalloonResult]: #datastoresearchballoonresult-structure
[DataStoreFetchMyInfosBalloonResult]: #datastorefetchmyinfosballoonresult-structure
[DataStoreFetchMyInfosAchievementResult]: #datastorefetchmyinfosachievementresult-structure
[DataStoreRatingInfo]: Data-Store-Protocol#datastoreratinginfo-structure

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