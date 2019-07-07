## [[NEX Protocols]] > [Data Store (0x73)](Data-Store-Protocol) > SMM 2

This page describes the methods that are only seen in Super Mario Maker 2. This page is incomplete. Any help would be appreciated.

| Method ID | Method Name |
| --- | --- |
| 47 | [RegisterUser](#47-registeruser) |
| 48 | [GetUsers](#48-getusers) |
| 49 | [SyncUserProfile](#49-syncuserprofile) |
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
| 131 | [GetUserOrCourse](#131-getuserorcourse) |
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

# (48) GetUsers
## Request
| Type | Description |
| --- | --- |
| [GetUsersParam](#getusersparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[UserInfo]&gt; | Users |
| [List]&lt;[Result]&gt; | Result codes |

# (49) SyncUserProfile
## Request
| Type | Description |
| --- | --- |
| [SyncUserProfileParam](#syncuserprofileparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [SyncUserProfileResult](#syncuserprofileresult-structure) | Result |

# (131) GetUserOrCourse
## Request
| Type | Description |
| --- | --- |
| [GetUserOrCourseParam](#getuserorcourseparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [UserInfo] | User info |
| [CourseInfo] | Course info |

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

## GetUsersParam ([Structure])
| Type | Name |
| --- | --- |
| [List]&lt;[PID]&gt; | userPIDs |
| Uint32 | resultOption |

## SyncUserProfileParam ([Structure])
| Type | Description |
| --- | --- |
| [String] | Unknown |
| [UnknownStruct1] | Unknown |
| [qBuffer] | Unknown |
| Uint8 | Unknown |
| [String] | Unknown |
| Bool | Unknown |
| Bool | Unknown |
| [String] | Unknown |
| Uint32 | Unknown |

## SyncUserProfileResult ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| [String] | Unknown |
| [UnknownStruct1] | Unknown |
| [qBuffer] | Unknown |
| Uint8 | Unknown |
| [String] | Unknown |
| Uint8 | Unknown |
| Bool | Unknown |
| Bool | Unknown |

## GetUserOrCourseParam ([Structure])
| Type | Name |
| --- | --- |
| [String] | codeString |
| Uint32 | userResultOption |
| Uint32 | courseResultOption |

## UserInfo ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| [String] | Unknown |
| [String] | Unknown |
| [UnknownStruct1] | Unknown |
| [qBuffer] | Unknown |
| [String] | Unknown |
| Uint8 | Unknown |
| Uint64 | Unknown |
| [DateTime] | Unknown |
| Bool | Unknown |
| Bool | Unknown |
| Bool | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| [List]&lt;[BadgeInfo](#badgeinfo-structure)&gt; | Badge info |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |

## UserInfo ([Structure])
| Type | Description |
| --- | --- |
| Uint16 | Unknown |
| Uint8 | Unknown |

## CourseInfo ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| [String] | Unknown |
| Uint64 | Unknown |
| [String] | Unknown |
| [String] | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| [DateTime] | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Uint32 | Unknown |
| Uint16 | Unknown |
| Uint16 | Unknown |
| [qBuffer] | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| [UnknownStruct2] | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| [Buffer] | Unknown |
| [String] | Unknown |

## UnknownStruct1 ([Structure])
| Type | Description |
| --- | --- |
| Uint16 | Unknown |
| Uint16 | Unknown |
| Uint16 | Unknown |
| Uint16 | Unknown |

## UnknownStruct2 ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Uint32 | Unknown |

## UnknownStruct3 ([Structure])
| Type | Description |
| --- | --- |
| [String] | Unknown |
| Uint8 | Unknown |
| Uint32 | Unknown |

[UnknownStruct1]: #unknownstruct1-structure
[UnknownStruct2]: #unknownstruct2-structure
[UnknownStruct3]: #unknownstruct3-structure

[UserInfo]: #userinfo-structure
[CourseInfo]: #courseinfo-structure

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