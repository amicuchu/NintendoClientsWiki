## [[NEX Protocols]] > [Data Store (0x73)](Data-Store-Protocol) > SMM

This page describes the methods that are only seen in Super Mario Maker. Most method and structure names listed here are not the official names, they are merely guesses.

| Method ID | Method Name |
| --- | --- |
| 45 | [GetFileServerObjectInfos](#45-getfileserverobjectinfos) |
| 46 | ? |
| 47 | ? |
| 48 | ? |
| 49 | ? |
| 50 | [GetInfoStuff](#50-getinfostuff) |
| 51 | ? |
| 52 | ? |
| 53 | ? |
| 54 | ? |
| 55 | ? |
| 56 | ? |
| 57 | [CompletePostObjectEx](#57-completepostobjectex) |
| 58 | ? |
| 59 | ? |
| 60 | ? |
| 61 | ? |
| 62 | ? |
| 63 | ? |
| 64 | ? |
| 65 | ? |
| 66 | ? |
| 67 | ? |
| 68 | ? |
| 69 | ? |
| 70 | ? |
| 71 | ? |
| 72 | ? |
| 73 | ? |
| 74 | ? |
| 75 | ? |
| 76 | ? |
| 77 | ? |
| 78 | ? |
| 79 | ? |
| 80 | ? |
| 81 | ? |
| 82 | ? |
| 83 | ? |
| 84 | ? |
| 85 | ? |
| 86 | ? |
| 87 | ? |

# (45) GetFileServerObjectInfos
## Request
| Type | Description |
| --- | --- |
| [List]&lt;Uint64&gt; | Object ids |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[DataStoreFileServerObjectInfo](#datastorefileserverobjectinfo)&gt; | Object infos |

# (50) GetInfoStuff
## Request
| Type | Description |
| --- | --- |
| [DataStoreGetInfoStuffParam](#datastoregetinfostuffparam-structure) | Param |

# (57) CompletePostObjectEx
## Request
| Type | Description |
| --- | --- |
| [DataStoreCompletePostParam] | Complete post param |

## Response
| Type | Description |
| --- | --- |
| [String] | Unknown |

# Types
## DataStoreFileServerObjectInfo ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| [DataStoreReqGetInfo] | GET request info |

## DataStoreGetInfoStuffParam ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| [List]&lt;Uint64&gt; | Unknown |
| Uint8 | Unknown |

## DataStoreInfoStuff ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| Uint32 | Unknown |
| [DataStoreMetaInfo] | Meta info |

[DataStoreCompletePostParam]: Data-Store-Protocol#datastorecompletepostparam-structure
[DataStoreReqGetInfo]: Data-Store-Protocol#datastorereqgetinfo-structure
[DataStoreMetaInfo]: Data-Store-Protocol#datastoremetainfo-structure

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