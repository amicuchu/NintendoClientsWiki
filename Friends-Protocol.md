[[NEX Protocols]] > Friends (0x14)
---

This protocol is implemented on Nintendo game servers, but no game seems to have the code to use this protocol.

| Method ID | Method Name |
| --- | --- |
| 1 | [AddFriend](#1-addfriend) |
| 2 | [AddFriendByName](#2-addfriendbyname) |
| 3 | [AddFriendWithDetails](#3-addfriendwithdetails) |
| 4 | [AddFriendByNameWithDetails](#4-addfriendbynamewithdetails) |
| 5 | [AcceptFriendship](#5-acceptfriendship) |
| 6 | [DeclineFriendship](#6-declinefriendship) |
| 7 | [BlackList](#7-blacklist) |
| 8 | [BlackList](#8-blacklist) |
| 9 | [ClearRelationship](#9-clearrelationship) |
| 10 | [UpdateDetails](#10-updatedetails) |
| 11 | [GetList](#11-getlist) |
| 12 | [GetDetailedList](#12-getdetailedlist) |
| 13 | [GetRelationships](#13-getrelationships) |

# (1) AddFriend
## Request
| Type | Name |
| --- | --- |
| Uint32 | uiPlayer |
| Uint32 | uiDetails |
| [String] | strMessage |

## Response
| Type | Name |
| --- | --- |
| Bool | %retval% |

# (2) AddFriendByName
## Request
| Type | Name |
| --- | --- |
| [String] | strPlayerName |
| Uint32 | uiDetails |
| [String] | strMessage |

## Response
| Type | Name |
| --- | --- |
| Bool | %retval% |

# (3) AddFriendWithDetails
## Request
| Type | Name |
| --- | --- |
| Uint32 | uiPlayer |
| Uint32 | uiDetails |
| [String] | strMessage |

## Response
| Type | Name |
| --- | --- |
| [RelationshipData](#relationshipdata) | relationshipData |

# (4) AddFriendByNameWithDetails
## Request
| Type | Name |
| --- | --- |
| Uint32 | uiPlayer |
| Uint32 | uiDetails |
| [String] | strMessage |

## Response
| Type | Name |
| --- | --- |
| [RelationshipData](#relationshipdata) | relationshipData |

# (5) AcceptFriendship
## Request
| Type | Name |
| --- | --- |
| Uint32 | uiPlayer |

## Response
| Type | Name |
| --- | --- |
| Bool | %retval% |

# (6) DeclineFriendship
## Request
| Type | Name |
| --- | --- |
| Uint32 | uiPlayer |

## Response
| Type | Name |
| --- | --- |
| Bool | %retval% |

# (7) BlackList
## Request
| Type | Name |
| --- | --- |
| Uint32 | uiPlayer |
| Uint32 | uiDetails |

## Response
| Type | Name |
| --- | --- |
| Bool | %retval% |

# (8) BlackListByName
## Request
| Type | Name |
| --- | --- |
| [String] | strPlayerName |
| Uint32 | uiDetails |

## Response
| Type | Name |
| --- | --- |
| Bool | %retval% |

# (9) ClearRelationship
## Request
| Type | Name |
| --- | --- |
| Uint32 | uiPlayer |

## Response
| Type | Name |
| --- | --- |
| Bool | %retval% |

# (10) UpdateDetails
## Request
| Type | Name |
| --- | --- |
| Uint32 | uiPlayer |
| Uint32 | uiDetails |

## Response
| Type | Name |
| --- | --- |
| Bool | %retval% |

# (11) GetList
## Request
| Type | Name |
| --- | --- |
| Uint8 | byRelationship |
| Bool | bReversed |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;Uint32&gt; | lstFriendsList |

# (12) GetDetailedList
## Request
| Type | Name |
| --- | --- |
| Uint8 | byRelationship |
| Bool | bReversed |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[FriendData](#frienddata)&gt; | lstFriendsList |

# (13) GetRelationships
## Request
| Type | Name |
| --- | --- |
| [ResultRange] | resultRange |

## Response
| Type | Name |
| --- | --- |
| Uint32 | uiTotalCount |
| [List]&lt;[RelationshipData](#relationshipdata)&gt; | lstRelationshipsList |

# Types
## FriendData
| Type | Name |
| --- | --- |
| Uint32 | m_pid |
| [String] | m_strName |
| Uint8 | m_byRelationship |
| Uint32 | m_uiDetails |
| [String] | m_strStatus |

## RelationshipData
| Type | Name |
| --- | --- |
| Uint32 | m_pid |
| [String] | m_strName |
| Uint8 | m_byRelationship |
| Uint32 | m_uiDetails |
| Uint8 | m_byStatus |

[List]: NEX-Common-Types#list
[String]: NEX-Common-Types#string
[ResultRange]: NEX-Common-Types#resultrange-structure