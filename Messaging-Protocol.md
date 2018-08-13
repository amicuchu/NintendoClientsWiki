## [[NEX Protocols]] > Messaging (0x17)

| Method ID | Method Name |
| --- | --- |
| 1 | [DeliverMessage](#1-delivermessage) |
| 2 | [GetNumberOfMessages](#2-getnumberofmessages) |
| 3 | [GetMessagesHeaders](#3-getmessagesheaders) |
| 4 | [RetrieveAllMessagesWithinRange](#4-retrieveallmessageswithinrange) |
| 5 | [RetrieveMessages](#5-retrievemessages) |
| 6 | [DeleteMessages](#6-deletemessages) |
| 7 | [DeleteAllMessages](#7-deleteallmessages) |

# (1) DeliverMessage
## Request
| Type | Name |
| --- | --- |
| [Data] | oUserMessage |

## Response
| Type | Name |
| --- | --- |
| [Data] | oModifiedMessage |
| [List]&lt;Uint32&gt; | lstSandboxNodeId |
| [List]&lt;[PID]&gt; | lstParticipants |

# (2) GetNumberOfMessages
## Request
| Type | Name |
| --- | --- |
| [MessageRecipient](#messagerecipient) | recipient |

## Response
| Type | Name |
| --- | --- |
| Uint32 | uiNbMessages |

# (3) GetMessagesHeaders
## Request
| Type | Name |
| --- | --- |
| [MessageRecipient](#messagerecipient) | recipient |
| [ResultRange] | range |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[UserMessage](#usermessage)&gt; | lstMsgHeaders |

# (4) RetrieveAllMessagesWithinRange
## Request
| Type | Name |
| --- | --- |
| [MessageRecipient](#messagerecipient) | recipient |
| [ResultRange] | range |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[Data]&gt; | lstMessages |

# (5) RetrieveMessages
## Request
| Type | Name |
| --- | --- |
| [MessageRecipient](#messagerecipient) | recipient |
| [List]&lt;Uint32&gt; | lstMsgIDs |
| Bool | bLeaveOnServer |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[Data]&gt; | lstMessages |

# (6) DeleteMessages
## Request
| Type | Name |
| --- | --- |
| [MessageRecipient](#messagerecipient) | recipient |
| [List]&lt;Uint32&gt; | lstMessagesToDelete |

## Response
This method does not return anything.

# (7) DeleteAllMessages
## Request
| Type | Name |
| --- | --- |
| [MessageRecipient](#messagerecipient) | recipient |

## Response
| Type | Name |
| --- | --- |
| Uint32 | uiNbDeletedMessages |

# Types
## MessageRecipient
| Type | Name |
| --- | --- |
| Uint32 | m_uiRecipientType |
| [PID] | m_principalId |
| Uint32 | m_gatheringId |

## UserMessage
| Type | Name |
| --- | --- |
| Uint32 | m_uiID |
| Uint32 | m_uiParentID |
| [PID] | m_pidSender |
| [DateTime] | m_receptiontime |
| Uint32 | m_uiLifeTime |
| Uint32 | m_uiFlags |
| [String] | m_strSubject |
| [String] | m_strSender |
| [MessageRecipient](#messagerecipient) | m_messageRecipient |

[String]: NEX-Common-Types#string
[DateTime]: NEX-Common-Types#date-time
[Data]: NEX-Common-Types#any-data-holder
[List]: NEX-Common-Types#list
[PID]: NEX-Common-Types#pid
[ResultRange]: NEX-Common-Types#result-range