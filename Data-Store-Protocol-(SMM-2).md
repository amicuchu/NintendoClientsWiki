## [[NEX Protocols]] > [Data Store (0x73)](Data-Store-Protocol) > SMM 2

This page describes the methods that are only seen in Super Mario Maker 2. This page is incomplete. Any help would be appreciated.

| Method ID | Method Name |
| --- | --- |
| 47 | [RegisterUser](#47-registeruser) |
| 48 | [GetUsers](#48-getusers) |
| 49 | [SyncUserProfile](#49-syncuserprofile) |
| 50 | [Method50](#50-method50) |
| 51 | [Method51](#51-method51) |
| 52 | [Method52](#52-method52) |
| 53 | [SearchUsersPlayedCourse](#53-searchusersplayedcourse) |
| 54 | [SearchUsersClearedCourse](#54-searchusersclearedcourse) |
| 55 | [SearchUsersPositiveRatedCourse](#55-searchuserspositiveratedcourse) |
| 56 | [SearchUsersFollowee](#56-searchusersfollowee) |
| 57 | [Method57](#57-method57) |
| 58 | [Method58](#58-method58) |
| 59 | [UpdateLastLoginTime](#59-updatelastlogintime) |
| 60 | [Method60](#60-method60) |
| 61 | [Method61](#61-method61) |
| 62 | [Method62](#62-method62) |
| 63 | [GetMiiClothes](#63-getmiiclothes) |
| 64 | ? |
| 65 | [GetUserNameNgType](#65-getusernamengtype) |
| 66 | ? |
| 67 | ? |
| 68 | ? |
| 69 | UpdateCourseTag |
| 70 | [GetCourseInfo](#70-getcourseinfo) |
| 71 | [SearchCoursesPointRanking](#71-searchcoursespointranking) |
| 72 | SearchCoursesAdvanced |
| 73 | [SearchCoursesLatest](#73-searchcourseslatest) |
| 74 | SearchCoursesPostedBy |
| 75 | SearchCoursesPositiveRatedBy |
| 76 | SearchCoursesPlayedBy |
| 77 | SearchCoursesBattleMode |
| 78 | ? |
| 79 | [SearchCoursesEndlessMode](#79-searchcoursesendlessmode) |
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
| 95 | [Method95](#95-method95) |
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
| 108 | [Method108](#108-method108) |
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
| 123 | Follow |
| 124 | Unfollow |
| 125 | GetNewNotification |
| 126 | ? |
| 127 | ? |
| 128 | ReadNgCourseNotification |
| 129 | GetNgCourseNotification |
| 130 | ? |
| 131 | [GetUserOrCourse](#131-getuserorcourse) |
| 132 | ? |
| 133 | ? |
| 134 | [Method134](#134-method134) |
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

# (50) Method50
## Request
| Type | Description |
| --- | --- |
| [MethodParam50](#methodparam50-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[UserInfo]&gt; | Users |
| [List]&lt;Uint32&gt; | Unknown |
| Bool | Ünknown |

# (51) Method51
## Request
| Type | Description |
| --- | --- |
| [MethodParam51](#methodparam51-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[UserInfo]&gt; | Users |
| [List]&lt;Uint32&gt; | Unknown |
| Bool | Ünknown |

# (52) Method52
## Request
| Type | Description |
| --- | --- |
| [MethodParam52](#methodparam52-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[UserInfo]&gt; | Users |
| [List]&lt;Uint32&gt; | Unknown |
| Bool | Unknown |

# (53) SearchUsersPlayedCourse
## Request
| Type | Description |
| --- | --- |
| [SearchUsersPlayedCourseParam](#searchusersplayedcourseparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[UserInfo]&gt; | Users |

# (54) SearchUsersClearedCourse
## Request
| Type | Description |
| --- | --- |
| [SearchUsersClearedCourseParam](#searchusersclearedcourseparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[UserInfo]&gt; | Users |

# (55) SearchUsersPositiveRatedCourse
## Request
| Type | Description |
| --- | --- |
| [SearchUsersPositiveRatedCourse](#searchuserspositiveratedcourseparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[UserInfo]&gt; | Users |

# (56) SearchUsersFollowee
## Request
| Type | Description |
| --- | --- |
| [SearchUsersFolloweeParam](#searchusersfolloweeparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[UserInfo]&gt; | Users |
| Bool | Unknown |

# (57) Method57
## Request
| Type | Description |
| --- | --- |
| [MethodParam57](#methodparam57-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[UserInfo]&gt; | Users |
| [List]&lt;Uint32&gt; | Unknown |
| Bool | Unknown |

# (58) Method58
## Request
| Type | Description |
| --- | --- |
| [MethodParam58](#methodparam58-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[UserInfo]&gt; | Users |
| [List]&lt;Uint32&gt; | Unknown |
| Bool | Unknown |

# (59) Method59
## Request
This method does not take any parameters.

## Response
This method does not return anything.

# (60) Method60
## Request
This method does not take any parameters.

## Response
| Type | Description |
| --- | --- |
| Bool | Unknown |
| Uint32 | Unknown |

# (61) Method61
## Request
| Type | Description |
| --- | --- |
| [MethodParam61](#methodparam61-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [MethodResult61](#methodresult61-structure) | Result |

# (62) Method62
## Request
| Type | Description |
| --- | --- |
| [List]&lt;[MethodParam62](#methodparam62-structure)&gt; | Param |

## Response
This method does not return anything.

# (63) GetMiiClothes
## Request
This method does not take any parameters.

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[MiiClothes]&gt; | Mii clothes |

# (65) GetUserNameNgType
## Request
This method does not take any parameters.

## Response
| Type | Description |
| --- | --- |
| Uint8 | Type |

# (70) GetCourseInfo
## Request
| Type | Description |
| --- | --- |
| [GetCourseInfoParam](#getcourseinfoparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[CourseInfo]&gt; | Course info |
| [List]&lt;[Result]&gt; | Result codes |

# (71) SearchCoursesPointRanking
## Request
| Type | Description |
| --- | --- |
| [SearchCoursesPointRankingParam](#searchcoursespointrankingparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[CourseInfo]&gt; | Course info |
| [List]&lt;Uint32&gt; | Ranks |
| Bool | Result |

# (73) SearchCoursesLatest
## Request
| Type | Description |
| --- | --- |
| [SearchCoursesLatestParam](#searchcourseslatestparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[CourseInfo]&gt; | Courses |
| Bool | Unknown |

# (79) SearchCoursesEndlessMode
## Request
| Type | Description |
| --- | --- |
| [SearchCoursesEndlessModeParam](#searchcoursesendlessmodeparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[CourseInfo]&gt; | Courses |

# (95) Method95
## Request
| Type | Description |
| --- | --- |
| Uint64 | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[CommentInfo]&gt; | Comments |

# (108) Method108
## Request
This method does not take any parameters.

## Response
| Type | Description |
| --- | --- |
| [MethodResult108](#methodresult108-structure) | Result |

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

# (134) Method134
## Request
| Type | Description |
| --- | --- |
| Uint8 | Unknown |

## Response
| Type | Description |
| --- | --- |
| [MethodResult134](#methodresult134-structure) | Result |

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
| [String] | Username |
| [UnknownStruct1] | Unknown |
| [qBuffer] | Unknown |
| Uint8 | Unknown |
| [String] | Country code |
| Bool | Unknown |
| Bool | Unknown |
| [String] | Unknown |
| Uint32 | Unknown |

## SyncUserProfileResult ([Structure])
| Type | Description |
| --- | --- |
| [PID] | User id |
| [String] | Username |
| [UnknownStruct1] | Unknown |
| [qBuffer] | Unknown |
| Uint8 | Unknown |
| [String] | Country code |
| Uint8 | Unknown |
| Bool | Unknown |
| Bool | Unknown |

## MethodParam50 ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| [Buffer] | Unknown |
| [ResultRange] | Result range |

## MethodParam51 ([Structure])
| Type | Description |
| --- | --- |
| Uint8 | Unknown |
| Uint32 | Unknown |
| [Buffer] | Unknown |
| [ResultRange] | Unknown |

## MethodParam52 ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| [Buffer] | Unknown |
| [ResultRange] | Unknown |

## SearchUsersPlayedCourseParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint32 | resultOption |
| Uint32 | count |

## SearchUsersClearedCourseParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint32 | resultOption |
| Uint32 | count |

## SearchUsersPositiveRatedCourseParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint32 | resultOption |
| Uint32 | count |

## SearchUsersFolloweeParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | resultOption |
| [ResultRange] | resultRange |

## MethodParam57 ([Structure])
| Type | Description |
| --- | --- |
| Uint8 | Unknown |
| Uint32 | Unknown |
| [Buffer] | Unknown |
| [ResultRange] | Unknown |

## MethodParam58 ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| [ResultRange] | Unknown |
| [Buffer] | Unknown |

## MethodParam61 ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Uint32 | Unknown |

## MethodResult61 ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Bool | Unknown |
| Uint32 | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| Bool | Unknown |
| Uint32 | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |

## MethodParam62 ([Structure])
| Type | Description |
| --- | --- |
| Uint16 | Unknown |
| Uint16 | Unknown |
| Bool | Unknown |

## GetCourseInfoParam ([Structure])
| Type | Description |
| --- | --- |
| [List]&lt;Uint64&gt; | Data ids |
| Uint32 | Result options |

## SearchCoursesPointRankingParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | resultOption |
| [ResultRange] | resultRange |
| Uint8 | preferCourseDifficulty |
| [List]&lt;Uint8&gt; | rejectRegionIds |

## SearchCoursesLatestParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | resultOption |
| [ResultRange] | resultRange |

## SearchCoursesEndlessModeParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | resultOption |
| Uint32 | count |
| Uint8 | difficulty |

## MethodResult108 ([Structure])
| Type | Description |
| --- | --- |
| [Map]&lt;Uint8, [UnknownStruct4]&gt; | Unknown |
| [Map]&lt;Uint8, [UnknownStruct5]&gt; | Unknown |

## GetUserOrCourseParam ([Structure])
| Type | Name |
| --- | --- |
| [String] | codeString |
| Uint32 | userResultOption |
| Uint32 | courseResultOption |

## MethodResult134 ([Structure])
| Type | Description |
| --- | --- |
| [List]&lt;[UnknownStruct6]&gt; | Unknown |
| Uint32 | Unknown |

## UserInfo ([Structure])
| Type | Description |
| --- | --- |
| [PID] | User id |
| [String] | User code |
| [String] | User name |
| [UnknownStruct1] | Unknown |
| [qBuffer] | Unknown |
| [String] | Country code |
| Uint8 | Region id |
| [DateTime] | Last active time |
| Bool | Unknown |
| Bool | Unknown |
| Bool | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| [List]&lt;[BadgeInfo]&gt; | Badge info |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |

## BadgeInfo ([Structure])
| Type | Description |
| --- | --- |
| Uint16 | Unknown |
| Uint8 | Unknown |

## CourseInfo ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Data id |
| [String] | Level code |
| [PID] | Owner id |
| [String] | Level name |
| [String] | Description |
| Uint8 | [Game style](#game-style) |
| Uint8 | [Course theme](#course-theme) |
| [DateTime] | Upload time |
| Uint8 | Difficulty (0-3) |
| Uint8 | First [tag](#course-tag) |
| Uint8 | Second [tag](#course-tag) |
| Uint8 | Unknown |
| Uint32 | [Clear condition](#clear-condition) |
| Uint16 | Clear condition magnitude |
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
| [UnknownStruct3] | Unknown |
| [UnknownStruct3] | Unknown |

### Game Style
| Value | Description |
| --- | --- |
| 0 | SMB1 |
| 1 | SMB3 |
| 2 | SMW |
| 3 | NSMBU |
| 4 | SM3DW |

### Course Theme
| Value | Description |
| --- | --- |
| 0 | Overworld |
| 1 | Underground |
| 2 | Castle |
| 3 | Airship |
| 4 | Underwater |
| 5 | Ghost house |
| 6 | Snow |
| 7 | Desert |
| 8 | Sky |
| 9 | Forest |

### Course Tag
| Value | Description |
| --- | --- |
| 0 | None |
| 1 | Standard |
| 2 | Puzzle solving |
| 3 | Speedrun |
| 4 | Autoscroll |
| 5 | Auto mario |
| 6 | Short and sweet |
| 7 | Multiplayer versus |
| 8 | Themed |
| 9 | Music |

### Clear Condition
| Value | Description |
| --- | --- |
| 0 | None |
| 4042480826 | Kill skipsqueaks |
| 4116396131 | Collect coins |

## CommentInfo ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| [String] | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Uint64 | Unknown |
| Uint16 | Unknown |
| Uint16 | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Bool | Unknown |
| Bool | Unknown |
| [DateTime] | Unknown |
| [qBuffer] | Unknown |
| [String] | Unknown |
| [CommentPictureReqGetInfoWithoutHeaders] | Comment picture info |
| Uint16 | Unknown |
| Uint8 | Unknown |

## CommentPictureReqGetInfoWithoutHeaders ([Structure])
| Type | Description |
| --- | --- |
| [String] | Unknown |
| Uint8 | Unknown |
| Uint32 | Unknown |
| [Buffer] | Unknown |
| [String] | Unknown |

## MiiClothes ([Structure])
| Type | Description |
| --- | --- |
| Uint16 | Unknown |
| Uint16 | Unknown |
| Bool | Unknown |

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
| Uint64 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |

## UnknownStruct3 ([Structure])
| Type | Description |
| --- | --- |
| [String] | Unknown |
| Uint8 | Unknown |
| Uint32 | Unknown |
| [Buffer] | Unknown |
| [String] | Unknown |

## UnknownStruct4 ([Structure])
| Type | Description |
| --- | --- |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Uint32 | Unknown |
| [DateTime] | Unknown |
| [DateTime] | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |

## UnknownStruct5 ([Structure])
| Type | Description |
| --- | --- |
| Uint8 | Unknown |
| Uint32 | Unknown |

## UnknownStruct6 ([Structure])
| Type | Description |
| --- | --- |
| [String] | Unknown |
| [String] | Unknown |

[UnknownStruct1]: #unknownstruct1-structure
[UnknownStruct2]: #unknownstruct2-structure
[UnknownStruct3]: #unknownstruct3-structure
[UnknownStruct4]: #unknownstruct4-structure
[UnknownStruct5]: #unknownstruct5-structure
[UnknownStruct6]: #unknownstruct6-structure

[UserInfo]: #userinfo-structure
[CourseInfo]: #courseinfo-structure
[BadgeInfo]: #badgeinfo-structure
[CommentInfo]: #commentinfo-structure
[CommentPictureReqGetInfoWithoutHeaders]: #commentpicturereqgetinfowithoutheaders-structure
[MiiClothes]: #miiclothes-structure

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
[ResultRange]: NEX-Common-Types#result-range-structure