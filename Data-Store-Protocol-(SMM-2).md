## [[NEX Protocols]] > [Data Store (0x73)](Data-Store-Protocol) > SMM 2

This page describes the methods that are only seen in Super Mario Maker 2. Almost nothing is known about these methods yet. Any help would be appreciated.

| Method ID | Method Name |
| --- | --- |
| 47 | [RegisterUser](#47-registeruser) |
| 48 | GetUsers |
| 49 | SyncUserProfile |
| 50 | ? |
| 51 | ? |
| 52 | ? |
| 53 | SearchUsersPlayedCourse |
| 54 | SearchUsersClearedCourse |
| 55 | SearchUsersPositiveRatedCourse |
| 56 | SearchUsersFollowee |
| 57 | ? |
| 58 | ? |
| 59 | UpdateLastLoginTime |
| 60 | ? |
| 61 | ? |
| 62 | ? |
| 63 | GetMiiClothes |
| 64 | ? |
| 65 | GetUserNameNgType |
| 66 | ? |
| 67 | ? |
| 68 | ? |
| 69 | UpdateCourseTag |
| 70 | GetCourseInfo |
| 71 | SearchCoursesPointRanking |
| 72 | ? |
| 73 | SearchCoursesLatest |
| 74 | SearchCoursesPostedBy |
| 75 | SearchCoursesPositiveRatedBy |
| 76 | SearchCoursesPlayedBy |
| 77 | SearchCoursesBattleMode |
| 78 | ? |
| 79 | SearchCoursesEndlessMode |
| 80 | ? |
| 81 | SearchCoursesBestTime |
| 82 | SearchCoursesFolloweePostedBy |
| 83 | ? |
| 84 | ? |
| 85 | ? |
| 86 | ? |
| 87 | ? |
| 88 | ? |
| 89 | ? |
| 90 | ? |
| 91 | ? |
| 92 | ? |
| 93 | ? |
| 94 | SearchCommentsInOrder |
| 95 | ? |
| 96 | ? |
| 97 | ? |
| 98 | ? |
| 99 | PostPlayResultPersonal |
| 100 | PostPlayResultEntire |
| 101 | PostPlayResult |
| 102 | ? |
| 103 | ? |
| 104 | PostRating |
| 105 | PostRatingInfoAccumulated |
| 106 | PostRatingPersonal |
| 107 | PostRatingEntire |
| 108 | ? |
| 109 | ? |
| 110 | ? |
| 111 | ? |
| 112 | ? |
| 113 | ? |
| 114 | ? |
| 115 | ? |
| 116 | ? |
| 117 | ? |
| 118 | StartBattleMode |
| 119 | EndBattleMode |
| 120 | ? |
| 121 | ? |
| 122 | EndMultiClear |
| 123 | ? |
| 124 | ? |
| 125 | GetNewNotification |
| 126 | ? |
| 127 | ? |
| 128 | ReadNgCourseNotification |
| 129 | GetNgCourseNotification |
| 130 | ? |
| 131 | GetUserOrCourse |
| 132 | ? |
| 133 | ? |
| 134 | ? |
| 135 | ? |
| 136 | ? |
| 137 | ? |
| 138 | ? |
| 139 | ? |
| 140 | ? |
| 141 | ? |
| 142 | ? |
| 143 | GetAdditionalMiiClothesInfo |
| 144 | GetAdditionalMiiClothes |
| 145 | ? |
| 146 | ? |

# (47) RegisterUser
## Request
| Type | Description |
| --- | --- |
| [RegisterUserParam](#registeruserparam-structure) | Param |

## Response
This method does not return anything.

# Types
## RegisterUserParam ([Structure])
| Type | Description |
| --- | --- |
| [String] | Unknown |
| [UnknownStruct1] | Unknown |
| [qBuffer] | Unknown |
| Uint8 | Unknown |
| [String] | Unknown |
| [String] | Unknown |

## UnknownStruct1 ([Structure])
| Type | Description |
| --- | --- |
| Uint16 | Unknown |
| Uint16 | Unknown |
| Uint16 | Unknown |
| Uint16 | Unknown |

[UnknownStruct1]: #unknownstruct1-structure

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
[DateTime]: NEX-Common-Types#date-time
[Structure]: NEX-Common-Types#structure
[Data]: NEX-Common-Types#any-data-holder
[PID]: NEX-Common-Types#pid