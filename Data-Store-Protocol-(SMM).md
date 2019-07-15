## [[NEX Protocols]] > [Data Store (0x73)](Data-Store-Protocol) > SMM

This page describes the methods that are only seen in Super Mario Maker. Most method and structure names listed here are not the official names, they are merely guesses. This page is very incomplete. Any help would be appreciated.

| Method ID | Method Name |
| --- | --- |
| 45 | [GetFileServerObjectInfos](#45-getfileserverobjectinfos) |
| 46 | ? |
| 47 | ? |
| 48 | [Method48](#48-method48) |
| 49 | [Method49](#49-method49) |
| 50 | [Method50](#50-method50) |
| 51 | ? |
| 52 | ? |
| 53 | [Method53](#53-method53) |
| 54 | [Method54](#54-method54) |
| 55 | ? |
| 56 | ? |
| 57 | [Method57](#57-method57) |
| 58 | ? |
| 59 | [Method59](#59-method59) |
| 60 | [Method60](#60-method60) |
| 61 | [Method61](#61-method61) |
| 62 | ? |
| 63 | ? |
| 64 | [Method64](#64-method64) |
| 65 | [Method65](#65-method65) |
| 66 | [Method66](#66-method66) |
| 67 | [Method67](#67-method67) |
| 68 | [Method68](#68-method68) |
| 69 | ? |
| 70 | ? |
| 71 | [Method71](#71-method71) |
| 72 | [Method72](#72-method72) |
| 73 | ? |
| 74 | [Method74](#74-method74) |
| 75 | ? |
| 76 | [Method76](#76-method76) |
| 77 | ? |
| 78 | [Method78](#78-method78) |
| 79 | [Method79](#79-method79) |
| 80 | ? |
| 81 | [Method81](#81-method81) |
| 82 | [Method82](#method-82) |
| 83 | ? |
| 84 | ? |
| 85 | ? |
| 86 | ? |
| 87 | [Method87](#87-method87) |

# (45) GetFileServerObjectInfos
## Request
| Type | Description |
| --- | --- |
| [List]&lt;Uint64&gt; | Object ids |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[DataStoreFileServerObjectInfo](#datastorefileserverobjectinfo)&gt; | Object infos |

# (48) Method48
## Request
| Type | Description |
| --- | --- |
| [List]&lt;[UnknownStruct6]&gt; | Unknown |

## Response
This method does not return anything.

# (49) Method49
## Request
| Type | Description |
| --- | --- |
| [MethodParam49](#methodparam49-structure) | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[DataStoreInfoStuff]&gt; | Infos |
| [List]&lt;[Result]&gt; | Result codes |

# (50) Method50
## Request
| Type | Description |
| --- | --- |
| [MethodParam50](#methodparam50-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[DataStoreInfoStuff]&gt; | Infos |
| [List]&lt;[Result]&gt; | Result codes |

# (53) Method53
## Request
| Type | Description |
| --- | --- |
| [List]&lt;[UnknownStruct4]&gt; | Unknown |
| [List]&lt;[qBuffer]&gt; | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[Result]&gt; | Results |

# (54) Method54
## Request
| Type | Description |
| --- | --- |
| [UnknownStruct4] | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[qBuffer]&gt; | Unknown |

# (57) Method57
## Request
| Type | Description |
| --- | --- |
| [DataStoreCompletePostParam] | Complete post param |

## Response
| Type | Description |
| --- | --- |
| [String] | Unknown |

# (59) Method59
## Request
| Type | Description |
| --- | --- |
| [MethodParam59](#methodparam59-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [DataStoreReqPostInfo] | POST request info |

# (60) Method60
## Request
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| [UnknownStruct7] | Unknown |
| [List]&lt;[String]&gt; | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[DataStoreInfoStuff]&gt; | Infos |

# (61) Method61
## Request
| Type | Description |
| --- | --- |
| Uint32 | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;Uint32&gt; | Unknown |

# (64) Method64
## Request
| Type | Description |
| --- | --- |
| [UnknownStruct7] | Unknown |
| [List]&lt;[String]&gt; | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[DataStoreInfoStuff]&gt; | Infos |

# (65) Method65
## Request
| Type | Description |
| --- | --- |
| [UnknownStruct7] | Unknown |
| [List]&lt;[String]&gt; | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[DataStoreInfoStuff]&gt; | Infos |

# (66) Method66
## Request
| Type | Description |
| --- | --- |
| [UnknownStruct7] | Unknown |
| [List]&lt;[String]&gt; | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[DataStoreInfoStuff]&gt; | Infos |

# (67) Method67
## Request
| Type | Description |
| --- | --- |
| [UnknownStruct7] | Unknown |
| [List]&lt;[String]&gt; | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[DataStoreInfoStuff]&gt; | Infos |

# (68) Method68
## Request
| Type | Description |
| --- | --- |
| [UnknownStruct7] | Unknown |
| [List]&lt;[String]&gt; | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[DataStoreInfoStuff]&gt; | Infos |

# (71) Method71
## Request
| Type | Description |
| --- | --- |
| [MethodParam71](#methodparam71-structure) | Param |

## Response
This method does not return anything.

# (72) Method72
## Request
| Type | Description |
| --- | --- |
| [UnknownStruct2] | Unknown |

## Response
| Type | Description |
| --- | --- |
| [UnknownStruct3] | Unknown |

# (74) Method74
## Request
| Type | Description |
| --- | --- |
| Uint32 | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[String]&gt; | Unknown |

# (76) Method76
## Request
| Type | Description |
| --- | --- |
| [List]&lt;Uint64&gt; | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;Uint32&gt; | Unknown |

# (78) Method78
## Request
| Type | Description |
| --- | --- |
| [List]&lt;[UnknownStruct2]&gt; | Unknown |
| [DataStoreGetMetaParam] | Get meta param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[DataStoreMetaInfo]&gt; | Meta infos |
| [List]&lt;[UnknownStruct3]&gt; | Unknown |
| [List]&lt;[Result]&gt; | Results |

# (79) Method79
## Request
| Type | Description |
| --- | --- |
| Uint32 | Unknown |

## Response
| Type | Description |
| --- | --- |
| Bool | Unknown |

# (81) Method81
## Request
| Type | Description |
| --- | --- |
| [UnknownStruct7] | Unknown |
| [List]&lt;[String]&gt; | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[DataStoreInfoStuff]&gt; | Unknown |

# (82) Method82
## Request
| Type | Description |
| --- | --- |
| [UnknownStruct7] | Unknown |
| [List]&lt;[String]&gt; | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[DataStoreInfoStuff]&gt; | Unknown |

# (87) Method87
## Request
| Type | Description |
| --- | --- |
| [MethodParam87](#methodparam87-structure) | 

## Response
This method does not return anything.

# Types
## DataStoreFileServerObjectInfo ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| [DataStoreReqGetInfo] | GET request info |

## DataStoreInfoStuff ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| Uint32 | Unknown |
| [DataStoreMetaInfo] | Meta info |

## MethodParam49 ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| [UnknownStruct5] | Unknown |
| Uint8 | Unknown |
| [UnknownStruct] | Unknown |

## MethodParam50 ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| [List]&lt;Uint64&gt; | Unknown |
| Uint8 | Unknown |

## MethodParam59 ([Structure])
| Type | Description |
| --- | --- |
| [DataStorePreparePostParam] | Prepare post param |
| Uint64 | Unknown |
| [String] | Unknown |

## MethodParam71 ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Uint8 | Unknown |
| Uint32 | Unknown |

## MethodParam87 ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| [String] | Unknown |
| Uint8 | Unknown |
| [String] | Unknown |

## UnknownStruct ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| Uint32 | Unknown |

## UnknownStruct2 ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Uint8 | Unknown |

## UnknownStruct3 ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Uint8 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| [DateTime] | Unknown |
| [DateTime] | Unknown |

## UnknownStruct4 ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Uint32 | Unknown |

## UnknownStruct5 ([Structure])
| Type | Description |
| --- | --- |
| Uint8 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |

## UnknownStruct6 ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint16 | Unknown |

## UnknownStruct7 ([Structure])
| Type | Description |
| --- | --- |
| Uint8 | Unknown |
| [List]&lt;Uint32&gt; | Unknown |
| Uint8 | Unknown |
| [List]&lt;Uint32&gt; | Unknown |
| Uint16 | Unknown |
| [DateTime] | Unknown |
| [DateTime] | Unknown |
| [DateTime] | Unknown |
| [DateTime] | Unknown |
| Uint32 | Unknown |
| [List]&lt;[String]&gt; | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| [UnknownStruct] | Unknown |
| Uint8 | Unknown |
| Uint32 | Unknown |
| Bool | Unknown |


[DataStoreInfoStuff]: #datastoreinfostuff-structure
[UnknownStruct]: #unknownstruct-structure
[UnknownStruct2]: #unknownstruct2-structure
[UnknownStruct3]: #unknownstruct3-structure
[UnknownStruct4]: #unknownstruct4-structure
[UnknownStruct5]: #unknownstruct5-structure
[UnknownStruct6]: #unknownstruct6-structure
[UnknownStruct7]: #unknownstruct7-structure

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