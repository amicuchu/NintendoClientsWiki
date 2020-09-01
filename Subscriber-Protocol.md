## [[NEX Protocols]] > Subscriber (0x79)

| Method ID | Method Name |
| --- | --- |
| 1 | Hello |
| 2 | [PostContent](#2-postcontent) |
| 3 | [GetContent](#3-getcontent) |
| 4 | Follow |
| 5 | UnfollowAllAndFollow |
| 6 | Unfollow |
| 7 | GetFollowing |
| 8 | GetFollower |
| 9 | GetNumFollowers |
| 10 | GetTimeline |
| 11 | DeleteContent |
| 12 | [GetContentMulti](#12-getcontentmulti) |
| 13 | UpdateUserStatus |
| 14 | GetFriendUserStatuses |
| 15 | GetUserStatuses |

# (2) PostContent
## Request
| Type | Description |
| --- | --- |
| [SubscriberPostContentParam](#subscriberpostcontentparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| Uint64 | Unknown |

# (3) GetContent
## Request
| Type | Description |
| --- | --- |
| [SubscriberGetContentParam](#subscribergetcontentparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[SubscriberContent](#subscribercontent-structure)&gt; | Content |

# (12) GetContentMulti
## Request
| Type | Description |
| --- | --- |
| [List]&lt;[SubscriberGetContentParam](#subscribergetcontentparam-structure) | Param |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[List]&lt;[SubscriberContent](#subscribercontent-structure)&gt;&gt; | Content |

# Types
## SubscriberContent ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Unknown |
| [String] | Unknown |
| [qBuffer] | Unknown |
| Uint64 | Unknown |
| [List]&lt;[String]&gt; | Unknown |
| [DateTime] | Unknown |

## SubscriberGetContentParam ([Structure])
| Type | Description |
| --- | --- |
| [String] | Unknown |
| Uint32 | Unknown |
| Uint32 | Unknown |
| Uint64 | Unknown |

## SubscriberPostContentParam ([Structure])
| Type | Description |
| --- | --- |
| [List]&lt;[String]&gt; | Unknown |
| [String] | Unknown |
| [qBuffer] | Unknown |

[Result]: NEX-Common-Types#result
[String]: NEX-Common-Types#string
[PID]: NEX-Common-Types#pid
[DateTime]: NEX-Common-Types#datetime
[Data]: NEX-Common-Types#anydataholder
[List]: NEX-Common-Types#list
[ResultRange]: NEX-Common-Types#resultrange-structure
[Structure]: NEX-Common-Types#structure
[qBuffer]: NEX-Common-Types#qbuffer