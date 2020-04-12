## [[NEX Protocols]] > [Data Store (0x73)](Data-Store-Protocol) > SMM

This page describes the methods that are only seen in Super Mario Maker. The protocol has been renamed from `DataStoreProtocol` to `DataStoreCustomProtocol`.

| Method ID | Method Name |
| --- | --- |
| 46 | GetMetaByOwnerId |
| 47 | CustomSearchObject |
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
| 62 | [SetApplicationConfig](#62-setapplicationconfig) |
| 63 | [DeleteApplicationConfig](#63-deleteapplicationconfig) |
| 64 | LatestCourseSearchObject |
| 65 | FollowingsLatestCourseSearchObject |
| 66 | RecommendedCourseSearchObject |
| 67 | ScoreRangeCascadedSearchObject |
| 68 | SuggestedCourseSearchObject |
| 69 | PreparePostObjectWithOwnerIdAndDataId |
| 70 | CompletePostObjectWithOwnerId |
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
| 87 | [ReportCourse](#87-reportcourse) |

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
| Uint32 | [Category](#applicationconfigtype) |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;Uint32&gt; | Config |

# (62) SetApplicationConfig
## Request
| Type | Description |
| --- | --- |
| Uint32 | [Category](#applicationconfigtype) |
| Uint32 | Index |
| Uint32 | Value |

## Response
This method does not return anything.

# (63) DeleteApplicationConfig
## Request
| Type | Description |
| --- | --- |
| Uint32 | [Category](#applicationconfigtype) |
| Uint32 | Index |

## Response
This method does not return anything.

# (74) GetApplicationConfigString
## Request
| Type | Description |
| --- | --- |
| Uint32 | [Category](#applicationconfigtypestring) |

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

# (87) ReportCourse
## Request
| Type | Description |
| --- | --- |
| [ReportCourseParam](#reportcourseparam-structure) | Param |

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

# Enums
## ApplicationConfigType
| Value | Description |
| --- | --- |
| 0 | Settings |
| 1 | PID |
| 2 | First clear time |
| 3 - 127 | Unused |

## ApplicationConfigTypeString
| Value | Description |
| --- | --- |
| 128 | Course ng word list first |
| 129 | Course ng word list second |
| 130 | Mii name ng word list |
| 131 - 255 | Unused |

<details><summary>Click to show the first word list</summary>

```
けされ
消され
削除され
リセットされ
BANされ
ＢＡＮされ
キミのコース
君のコース
きみのコース
い い ね
遊びます
地震
震災
被災
津波
バンされ
い~ね
震度
じしん
banされ
くわしくは
詳しくは
ちんちん
ち0こ
bicth
い.い．ね
ナイ～ス
い&い
い-いね
いぃね
nigger
ngger
star if u
Star if u
Star if you
star if you
PENlS
マンコ
butthole
LILI
vagina
vagyna
うんち
うんこ
ウンコ
Ｉｉｎｅ
EENE
まんこ
ウンチ
niglet
nigglet
please like
きんたま
Butthole
llね
iいね
give a star
ちんぽ
亀頭
penis
ｳﾝｺ
plz more stars
star plz
い()ね
PLEASE star
Bitte Sterne
```
</details>

<details><summary>Click to show the second word list</summary>

```
ゼロから
０から
0から
い　　い　　ね
いい
東日本

大震
```
</details>

<details><summary>Click to show the mii name word list</summary>

```
いいね
下さい
ください
押して
おして
返す
かえす
星

してくれ
するよ
☆くれたら
☆あげます
★くれたら
★あげます
しね
ころす
ころされた
アナル
ファック
キンタマ
○ね
キチガイ
うんこ
KITIGAI
金玉
おっぱい
☆おす
☆押す
★おす
★押す
いいする
いいよ
イイネ
ケツ
うんち
かくせいざい
覚せい剤
シャブ
きんたま
ちんちん
おしっこ
ちんぽこ
ころして
グッド
グット
レ●プ
バーカ
きちがい
ちんげ
マンコ
まんこ
チンポ
クズ
ウンコ
ナイスおねがいします
penis
イイね
☆よろ
ナイス!して
ま/んこ
まん/こ
```

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