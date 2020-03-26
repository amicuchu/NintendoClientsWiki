## [[NEX Protocols]] > [Data Store (0x73)](Data-Store-Protocol) > SMM 2

This page describes the methods that are only seen in Super Mario Maker 2.

Some methods take a `resultOption` parameter. This parameter controls which fields are looked up in the database. Fields that are not specified in the `resultOption` parameter are usually returned as zero or empty.

| Method ID | Method Name |
| --- | --- |
| 47 | [RegisterUser](#47-registeruser) |
| 48 | [GetUsers](#48-getusers) |
| 49 | [SyncUserProfile](#49-syncuserprofile) |
| 50 | [SearchUsersUserPoint](#50-searchusersuserpoint) |
| 51 | [SearchUsersEndlessMode](#51-searchusersendlessmode) |
| 52 | [SearchUsersBattleMode](#52-searchusersbattlemode) |
| 53 | [SearchUsersPlayedCourse](#53-searchusersplayedcourse) |
| 54 | [SearchUsersClearedCourse](#54-searchusersclearedcourse) |
| 55 | [SearchUsersPositiveRatedCourse](#55-searchuserspositiveratedcourse) |
| 56 | [SearchUsersFollowee](#56-searchusersfollowee) |
| 57 | [SearchUsersClearRanking](#57-searchusersclearranking) |
| 58 | SearchUsersTermsRanking |
| 59 | [UpdateLastLoginTime](#59-updatelastlogintime) |
| 60 | [CanPostCourse](#60-canpostcourse) |
| 61 | [CanPostRatingAndComment](#61-canpostratingandcomment) |
| 62 | [UpdateMiiClothes](#62-updatemiiclothes) |
| 63 | [GetMiiClothes](#63-getmiiclothes) |
| 64 | PostActivityQuest |
| 65 | [GetUserNameNgType](#65-getusernamengtype) |
| 66 | [PreparePostObjectCourse](#66-preparepostobjectcourse) |
| 67 | CompletePostObjectCourse |
| 68 | CompletePostObjectsCourse |
| 69 | UpdateCourseTag |
| 70 | [GetCourses](#70-GetCourses) |
| 71 | [SearchCoursesPointRanking](#71-searchcoursespointranking) |
| 72 | SearchCoursesAdvanced |
| 73 | [SearchCoursesLatest](#73-searchcourseslatest) |
| 74 | SearchCoursesPostedBy |
| 75 | SearchCoursesPositiveRatedBy |
| 76 | SearchCoursesPlayedBy |
| 77 | SearchCoursesBattleMode |
| 78 | SearchCoursesBattleModeByDifficulty |
| 79 | [SearchCoursesEndlessMode](#79-searchcoursesendlessmode) |
| 80 | SearchCoursesFirstClear |
| 81 | SearchCoursesBestTime |
| 82 | SearchCoursesFolloweePostedBy |
| 83 | SearchCoursesTermsRanking |
| 84 | SearchCoursesPickUp |
| 85 | [GetCoursesEvent](#85-getcoursesevent) |
| 86 | [SearchCoursesEvent](#86-searchcoursesevent) |
| 87 | [ReadEventCourseList](#87-readeventcourselist) |
| 88 | PreparePostObjectCommentPicture |
| 89 | CompletePostObjectCommentPicture |
| 90 | CompletePostObjectsCommentPicture |
| 91 | PostCommentText |
| 92 | PostCommentStamp |
| 93 | DeleteComment |
| 94 | SearchCommentsInOrder |
| 95 | [SearchComments](#95-searchcomments) |
| 96 | PostPlayResult |
| 97 | PostPlayResults |
| 98 | PostPlayResultsAccumulated |
| 99 | PostPlayResultBattleModePersonal |
| 100 | PostPlayResultBattleModeEntire |
| 101 | PostPlayResultMultiClear |
| 102 | PostPlayResultEventCourse |
| 103 | GetDeathPositions |
| 104 | PostRatingInfo |
| 105 | PostRatingInfos|
| 106 | PostRatingInfoBattleModePersonal |
| 107 | PostRatingInfoBattleModeEntire |
| 108 | [GetEndlessModeStatus](#108-getendlessmodestatus) |
| 109 | InitEndlessMode |
| 110 | StartEndlessModeCourse |
| 111 | DominateEndlessModeCourse |
| 112 | PassEndlessModeCourse |
| 113 | SuspendEndlessMode |
| 114 | FinishEndlessMode |
| 115 | GetEndlessModePlayInfo |
| 116 | GetEndlessModeRank |
| 117 | [GetBattleModeRating](#117-getbattlemoderating) |
| 118 | StartBattleMode |
| 119 | EndBattleMode |
| 120 | ForceEndBattleMode |
| 121 | StartMultiClear |
| 122 | EndMultiClear |
| 123 | FollowUser |
| 124 | UnfollowUser |
| 125 | GetNewNotification |
| 126 | ReadNewNotification |
| 127 | GetNotification |
| 128 | ReadNotification |
| 129 | GetNgCourseNotification |
| 130 | GetOperatingInformation |
| 131 | [GetUserOrCourse](#131-getuserorcourse) |
| 132 | [PreparePostRelationObject](#132-preparepostrelationobject) |
| 133 | CompletePostRelationObject |
| 134 | [GetReqGetInfoHeadersInfo](#134-getreqgetinfoheadersinfo) |
| 135 | CanReportFromCourseInfo |
| 136 | CanReportFromCommentInfo |
| 137 | CanReportFromUserInfo |
| 138 | CanReportFromBugDetection |
| 139 | ReportFromCourseInfo |
| 140 | ReportFromCommentInfo |
| 141 | ReportFromUserInfo |
| 142 | ReportFromBugDetection |
| 143 | GetAdditionalMiiClothes |
| 144 | GetAdditionalMiiClothesReqGetInfos |
| 145 | DebugPreparePostObjectAdditionalMiiClothes |
| 146 | DebugCompletePostObjectAdditionalMiiClothes |
| 147 | SearchUsersOfficial |
| 148 | PostPlayResultCoop |
| 149 | PostPlayResultBattleModeFriendPersonal |
| 150 | PostPlayResultBattleModeFriendEntire |
| 151 | LoginCheck |
| 152 | UpdateLastLoginInfo |
| 153 | [GetEventCourseStamp](#153-geteventcoursestamp) |
| 154 | [GetEventCourseStatus](#154-geteventcoursestatus) |
| 155 | [ReadEventCourseResult](#155-readeventcourseghostresult) |
| 156 | [GetEventCourseHistogram](#156-geteventcoursehistogram) |
| 157 | [GetEventCourseGhost](#157-geteventcourseghost) |
| 158 | [DebugUploadEventCourseGhost](#158-debuguploadeventcourseghost) |

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

# (50) SearchUsersUserPoint
## Request
| Type | Description |
| --- | --- |
| [SearchUsersUserPointParam](#searchusersuserpointparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[UserInfo]&gt; | Users |
| [List]&lt;Uint32&gt; | Ranks |
| Bool | Result |

# (51) SearchUsersEndlessMode
## Request
| Type | Description |
| --- | --- |
| [SearchUsersEndlessModeParam](#searchusersendlessmodeparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[UserInfo]&gt; | Users |
| [List]&lt;Uint32&gt; | Unknown |
| Bool | Unknown |

# (52) SearchUsersBattleMode
## Request
| Type | Description |
| --- | --- |
| [SearchUsersBattleModeParam](#searchusersbattlemodeparam-structure) | Param |

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

# (57) SearchUsersClearRanking
## Request
| Type | Description |
| --- | --- |
| [SearchUsersClearRankingParam](#searchusersclearrankingparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[UserInfo]&gt; | Users |
| [List]&lt;Uint32&gt; | Unknown |
| Bool | Unknown |

# (59) UpdateLastLoginTime
## Request
This method does not take any parameters.

## Response
This method does not return anything.

# (60) CanPostCourse
## Request
This method does not take any parameters.

## Response
| Type | Description |
| --- | --- |
| Bool | Unknown |
| Uint32 | Unknown |

# (61) CanPostRatingAndComment
## Request
| Type | Description |
| --- | --- |
| [CanPostRatingAndCommentParam](#canpostratingandcommentparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [CanPostRatingAndCommentResult](#canpostratingandcommentresult-structure) | Result |

# (62) UpdateMiiClothes
## Request
| Type | Description |
| --- | --- |
| [List]&lt;[UpdateMiiClothesParam](#updatemiiclothesparam-structure)&gt; | Param |

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

# (66) PreparePostObjectCourse
## Request
| Type | Description |
| --- | --- |
| [PreparePostCourseParam](#preparepostcourseparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [DataStoreReqPostInfo] | Info |

# (70) GetCourses
## Request
| Type | Description |
| --- | --- |
| [GetCoursesParam](#getcoursesparam-structure) | Param |

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

# (85) GetCoursesEvent
## Request
| Type | Description |
| --- | --- |
| [GetCoursesParam](#getcoursesparam-structure) | Course param |
| [GetCoursesEventParam](#getcourseseventparam-structure) | Event param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[EventCourseInfo](#eventcourseinfo-structure)&gt; | Event courses |
| [List]&lt;[Result]&gt; | Results |

# (86) SearchCoursesEvent
## Request
| Type | Description |
| --- | --- |
| [SearchCoursesEventParam](#searchcourseseventparam-structure) | Event param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[EventCourseInfo](#eventcourseinfo-structure)&gt; | Event courses |

# (87) ReadEventCourseList
## Request
| Type | Description |
| --- | --- |
| [ReadEventCourseListParam](#readeventcourselistparam-structure) | Param |

## Response
This method does not return anything.

# (95) SearchComments
## Request
| Type | Description |
| --- | --- |
| Uint64 | Data id |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[CommentInfo]&gt; | Comments |

# (108) GetEndlessModeStatus
## Request
This method does not take any parameters.

## Response
| Type | Description |
| --- | --- |
| [EndlessModeStatus](#endlessmodestatus-structure) | Result |

# (117) GetBattleModeRating
## Request
This method does not take any parameters.

## Response
| Type | Description |
| --- | --- |
| Bool | Unknown |
| [BattleModeRating] | Rating 1 |
| [BattleModeRating] | Rating 2 |

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

# (132) PreparePostRelationObject
## Request
| Type | Description |
| --- | --- |
| [PreparePostRelationObjectParam](#preparepostrelationobjectparam-structure) | Info |

## Response
| Type | Description |
| --- | --- |
| [RelationObjectReqPostInfo](#relationobjectreqpostinfo-structure) | Param |

# (134) GetReqGetInfoHeadersInfo
This method returns headers that can be used to download relation files from the cloudfront datastore server.

## Request
| Type | Description |
| --- | --- |
| Uint8 | [Data type](#relation-data-type) |

#### Relation Data Type
| Value | Directory |
| --- | --- |
| 2 | /ds/1/relation_data/course_one_screen_thumbnail/ |
| 3 | /ds/1/relation_data/course_entire_thumbnail/ |
| 10 | /ds/1/comment/ |

## Response
| Type | Description |
| --- | --- |
| [ReqGetInfoHeadersInfo](#reqgetinfoheadersinfo-structure) | Info |

# (153) GetEventCourseStamp
## Request
This method does not take any parameters.

## Response
| Type | Description |
| --- | --- |
| Uint32 | Unknown |

# (154) GetEventCourseStatus
## Request
This method does not take any parameters.

## Response
| Type | Description |
| --- | --- |
| [EventCourseStatusInfo](#eventcoursestatusinfo-structure) | Status info |

# (155) ReadEventCourseResult
## Request
| Type | Description |
| --- | --- |
| Uint64 | Unknown |

## Response
This method does not return anything.

# (156) GetEventCourseHistogram
## Request
| Type | Description |
| --- | --- |
| [GetEventCourseHistogramParam](#geteventcoursehistogramparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [EventCourseHistogram](#eventcoursehistogram) | Histogram info |

# (157) GetEventCourseGhost
## Request
| Type | Description |
| --- | --- |
| [GetEventCourseGhostParam](#geteventcourseghostparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[EventCourseGhostInfo](#eventcourseghostinfo-structure)&gt; | Ghosts |

# (158) DebugUploadEventCourseGhost
## Request
| Type | Description |
| --- | --- |
| [DebugUploadEventCourseGhostParam](#debuguploadeventcourseghostparam-structure) | Param |

## Response
This method does not return anything.

# Types
## BadgeInfo ([Structure])
| Type | Description |
| --- | --- |
| Uint16 | Unknown |
| Uint8 | Unknown |

## BattleModeRating ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| Uint8 | Unknown |

## CanPostRatingAndCommentParam ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Uint32 | Unknown |

## CanPostRatingAndCommentResult ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Bool | Unknown |
| Uint32 | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| Bool | Unknown |
| Uint32 | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |

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
| Uint16 | Unknown |
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
| [String] | Url |
| Uint8 | Relation data type |
| Uint32 | Filesize |
| [Buffer] | Root ca cert |
| [String] | Filename |

## CourseInfo ([Structure])
| Type | Option | Description |
| --- | --- | --- |
| Uint64 | | Data id |
| [String] | | Level code |
| [PID] | | Owner id |
| [String] | | Level name |
| [String] | | Description |
| Uint8 | | [Game style](#game-style) |
| Uint8 | | [Course theme](#course-theme) |
| [DateTime] | | Upload time |
| Uint8 | | [Difficulty](#difficulty-level) |
| Uint8 | | First [tag](#course-tag) |
| Uint8 | | Second [tag](#course-tag) |
| Uint8 | | Unknown |
| Uint32 | | [Clear condition](#clear-condition) |
| Uint16 | | Clear condition magnitude |
| Uint16 | | Unknown |
| [qBuffer] | | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | `0x1` | [Play stats](#course-play-stats) |
| [Map]&lt;Uint8, Uint32&gt; | `0x2` | [Course ratings](#course-ratings) |
| [Map]&lt;Uint8, Uint32&gt; | `0x40` | Unknown |
| [CourseTimeStats](#coursetimestats-structure) | `0x4` | Time stats |
| [Map]&lt;Uint8, Uint32&gt; | `0x8` | [Comment stats](#comment-stats) |
| Uint8 | `0x10` | Unknown |
| Uint8 | `0x20` | Unknown |
| Uint8 | `0x10` | Unknown |
| Uint8 | `0x20` | Unknown |
| [RelationObjectReqGetInfo] | `0x80` | One-screen thumbnail |
| [RelationObjectReqGetInfo] | `0x100` | Entire thumbnail |

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

### Course Play Stats
| Key | Description |
| --- | --- |
| 0 | Plays |
| 1 | Attempts |
| 2 | Unknown |
| 3 | Clears |
| 4 | Plays (versus mode) |

### Course Ratings
| Key | Description |
| --- | --- |
| 0 | Hearts |
| 1 | Unknown |
| 2 | Unknown |

### Comment Stats
| Key | Description |
| --- | --- |
| 0 | Number of comments  |

## CourseTimeStats ([Structure])
| Type | Description |
| --- | --- |
| [PID] | User id of first completion |
| [PID] | User id of world record holder |
| Uint32 | World record (milliseconds) |
| Uint32 | Time of uploader (milliseconds) |

## DebugUploadEventCourseGhostParam ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Uint32 | Unknown |
| [String] | Unknown |

## EndlessModeStatus ([Structure])
| Type | Description |
| --- | --- |
| [Map]&lt;Uint8, [UnknownStruct4]&gt; | Unknown |
| [Map]&lt;Uint8, [UnknownStruct5]&gt; | Unknown |

## EventCourseGhostInfo ([Structure])
| Type | Description |
| --- | --- |
| [RelationObjectReqGetInfo] | Replay file |
| Uint32 | Unknown |
| Uint64 | Unknown |

## EventCourseHistogram ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| [List]&lt;Uint32&gt; | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| Uint32 | Unknown |

## EventCourseInfo ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| [String] | Unknown |
| [String] | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Bool | Unknown |
| Bool | Unknown |
| [DateTime] | Unknown |
| [DataStoreReqGetInfo] | GET request info |
| [Map]&lt;Uint8, Uint32&gt; | Unknown |
| [UnknownStruct6](#unknownstruct6-structure) | Unknown |
| Uint8 | Unknown |
| [UnknownStruct7](#unknownstruct7-structure) | Unknown |
| [UnknownStruct7](#unknownstruct7-structure) | Unknown |
| [DateTime] | Unknown |
| Uint8 | Unknown |
| Uint32 | Unknown |
| Uint16 | Unknown |
| Uint16 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| [RelationObjectReqGetInfo] | Unknown |
| [RelationObjectReqGetInfo] | Unknown |

## EventCourseStatusInfo ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Bool | Unknown |
| [DateTime] | Unknown |

## GetCoursesParam ([Structure])
| Type | Description |
| --- | --- |
| [List]&lt;Uint64&gt; | Data ids |
| Uint32 | Result options |

## GetCoursesEventParam ([Structure])
This structure is empty.

## GetEventCourseGhostParam ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| Uint32 | Unknown |
| Uint8 | Unknown |

## GetEventCourseHistogramParam ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |

## GetUserOrCourseParam ([Structure])
| Type | Name |
| --- | --- |
| [String] | codeString |
| Uint32 | userResultOption |
| Uint32 | courseResultOption |

## GetUsersParam ([Structure])
| Type | Name |
| --- | --- |
| [List]&lt;[PID]&gt; | userPIDs |
| Uint32 | resultOption |

## MiiClothes ([Structure])
| Type | Description |
| --- | --- |
| Uint16 | Unknown |
| Uint16 | Unknown |
| Bool | Unknown |

## PreparePostCourseParam ([Structure])
| Type | Description |
| --- | --- |
| [String] | Unknown |
| [String] | Unknown |
| Uint32 | Unknown |
| Bool | Unknown |
| Uint8 | Unknown |
| Uint8 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| [qBuffer] | Unknown |
| Uint8 | Unknown |
| Uint32 | Unknown |
| Uint16 | Unknown |
| Uint16 | Unknown |
| Bool | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| [List]&lt;[String]&gt; | Unknown |

## PreparePostRelationObjectParam ([Structure])
| Type | Name |
| --- | --- |
| [String] | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| [List]&lt;[String]&gt; | Unknown |

## ReadEventCourseListParam ([Structure])
| Type | Description |
| --- | --- |
| [DateTime] | Unknown |

## RegisterUserParam ([Structure])
| Type | Description |
| --- | --- |
| [String] | Username |
| [UnknownStruct1] | Unknown |
| [qBuffer] | Unknown |
| Uint8 | Region id |
| [String] | Country code |
| [String] | Pseudo device id |

## RelationObjectReqGetInfo ([Structure])
| Type | Description |
| --- | --- |
| [String] | Url |
| Uint8 | Relation data type |
| Uint32 | Filesize |
| [Buffer] | Root ca cert |
| [String] | Filename |

## RelationObjectReqPostInfo ([Structure])
| Type | Description |
| --- | --- |
| [String] | Unknown |
| [String] | Unknown |
| [List]&lt;[DataStoreKeyValue]&gt; | Headers |
| [List]&lt;[DataStoreKeyValue]&gt; | Form fields |
| [Buffer] | Unknown |

## ReqGetInfoHeadersInfo ([Structure])
| Type | Description |
| --- | --- |
| [List]&lt;[DataStoreKeyValue]&gt; | Headers |
| Uint32 | Expiration (seconds) |

## SearchCoursesEndlessModeParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | resultOption |
| Uint32 | count |
| Uint8 | difficulty |

## SearchCoursesEventParam ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Unknown |

## SearchCoursesLatestParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | resultOption |
| [ResultRange] | resultRange |

## SearchCoursesPointRankingParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | resultOption |
| [ResultRange] | resultRange |
| Uint8 | preferCourseDifficulty |
| [List]&lt;Uint8&gt; | rejectRegionIds |

## SearchUsersBattleModeParam ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Unknown |
| [Buffer] | Unknown |
| [ResultRange] | Unknown |

## SearchUsersClearedCourseParam ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | dataId |
| Uint32 | resultOption |
| Uint32 | count |

## SearchUsersClearRankingParam ([Structure])
| Type | Description |
| --- | --- |
| Uint8 | Unknown |
| Uint32 | Unknown |
| [Buffer] | Unknown |
| [ResultRange] | Unknown |

## SearchUsersEndlessModeParam ([Structure])
| Type | Description |
| --- | --- |
| Uint8 | Unknown |
| Uint32 | Unknown |
| [Buffer] | Unknown |
| [ResultRange] | Unknown |

## SearchUsersFolloweeParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | resultOption |
| [ResultRange] | resultRange |

## SearchUsersPlayedCourseParam ([Structure])
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

## SearchUsersUserPointParam ([Structure])
| Type | Description |
| --- | --- |
| Uint32 | Result option |
| [Buffer] | Unknown |
| [ResultRange] | Result range |

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

## UnknownStruct1 ([Structure])
| Type | Description |
| --- | --- |
| Uint16 | Unknown |
| Uint16 | Unknown |
| Uint16 | Unknown |
| Uint16 | Unknown |

## UnknownStruct3 ([Structure])
| Type | Description |
| --- | --- |
| Uint8 | Unknown |
| [DateTime] | Unknown |

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
| Uint64 | Unknown |
| Uint32 | Unknown |

## UnknownStruct7 ([Structure])
| Type | Description |
| --- | --- |
| [String] | Url |
| [List]&lt;[DataStoreKeyValue]&gt; | Headers |
| Uint32 | Filesize |
| [Buffer] | Root ca cert |
| [String] | Filename |

## UpdateMiiClothesParam ([Structure])
| Type | Description |
| --- | --- |
| Uint16 | Unknown |
| Uint16 | Unknown |
| Bool | Unknown |

## UserInfo ([Structure])
| Type | Option | Description |
| --- | --- | --- |
| [PID] | | User id |
| [String] | | Maker code |
| [String] | | User name |
| [UnknownStruct1] | `0x200` | Unknown |
| [qBuffer] | `0x4` | Unknown |
| [String] | | Country code |
| Uint8 | | Region id |
| [DateTime] | | Last active time |
| Bool | | Unknown |
| Bool | | Unknown |
| Bool | | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | `0x1` | [Play stats](#user-play-stats) |
| [Map]&lt;Uint8, Uint32&gt; | `0x2` | [Maker stats](#maker-stats) |
| [Map]&lt;Uint8, Uint32&gt; | `0x8` | [Endless mode highscores](#difficulty-level) |
| [Map]&lt;Uint8, Uint32&gt; | `0x10` | [Multiplayer stats](#multiplayer-stats) |
| [Map]&lt;Uint8, Uint32&gt; | `0x400` | Unknown |
| [List]&lt;[BadgeInfo]&gt; | `0x20` | Badge info |
| [Map]&lt;Uint8, Uint32&gt; | `0x40` | Unknown |
| [Map]&lt;Uint8, Uint32&gt; | `0x80` | Unknown |

Revision 1:

| Type | Option | Description |
| --- | --- | --- |
| Bool | | Unknown |
| [DateTime] | `0x1000` | Unknown |
| Bool | | Unknown |

Revision 2:

| Type | Option | Description |
| --- | --- | --- |
| [UnknownStruct3] | `0x2000` | Unknown |

### User Play Stats
| Key | Description |
| --- | --- |
| 0 | Plays |
| 1 | Clears |
| 2 | Attempts |
| 3 | Deaths |

### Maker Stats
| Key | Description |
| --- | --- |
| 0 | Hearts received |
| 1 | Maker points |

### Multiplayer Stats
| Key | Description |
| --- | --- |
| 0 | Multiplayer score |
| 2 | Versus plays |
| 3 | Versus wins |
| 10 | Coop plays |
| 11 | Coop wins |

## Difficulty Level
| Value | Description |
| --- | --- |
| 0 | Easy |
| 1 | Normal |
| 2 | Expert |
| 3 | Super expert |


[UnknownStruct1]: #unknownstruct1-structure
[UnknownStruct2]: #unknownstruct2-structure
[UnknownStruct3]: #unknownstruct3-structure
[UnknownStruct4]: #unknownstruct4-structure
[UnknownStruct5]: #unknownstruct5-structure

[UserInfo]: #userinfo-structure
[CourseInfo]: #courseinfo-structure
[BadgeInfo]: #badgeinfo-structure
[RelationObjectReqGetInfo]: #relationobjectreqgetinfo-structure
[CommentInfo]: #commentinfo-structure
[CommentPictureReqGetInfoWithoutHeaders]: #commentpicturereqgetinfowithoutheaders-structure
[MiiClothes]: #miiclothes-structure
[BattleModeRating]: #battlemoderating-structure

[DataStoreGetMetaParam]: Data-Store-Protocol#datastoregetmetaparam-structure
[DataStorePreparePostParam]: Data-Store-Protocol#datastorepreparepostparam-structure
[DataStoreCompletePostParam]: Data-Store-Protocol#datastorecompletepostparam-structure
[DataStoreReqGetInfo]: Data-Store-Protocol#datastorereqgetinfo-structure
[DataStoreReqPostInfo]: Data-Store-Protocol#datastorereqpostinfo-structure
[DataStoreMetaInfo]: Data-Store-Protocol#datastoremetainfo-structure
[DataStoreKeyValue]: Data-Store-Protocol#datastorekeyvalue-structure

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