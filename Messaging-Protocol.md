## [NEX Protocols](NEX-Protocols.md) > Messaging (0x17)

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
| [MessageRecipient](#messagerecipient-structure) | recipient |

## Response
| Type | Name |
| --- | --- |
| Uint32 | uiNbMessages |

# (3) GetMessagesHeaders
## Request
| Type | Name |
| --- | --- |
| [MessageRecipient](#messagerecipient-structure) | recipient |
| [ResultRange] | range |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[UserMessage](#usermessage-structure)&gt; | lstMsgHeaders |

# (4) RetrieveAllMessagesWithinRange
## Request
| Type | Name |
| --- | --- |
| [MessageRecipient](#messagerecipient-structure) | recipient |
| [ResultRange] | range |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[Data]&gt; | lstMessages |

# (5) RetrieveMessages
## Request
| Type | Name |
| --- | --- |
| [MessageRecipient](#messagerecipient-structure) | recipient |
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
| [MessageRecipient](#messagerecipient-structure) | recipient |
| [List]&lt;Uint32&gt; | lstMessagesToDelete |

## Response
This method does not return anything.

# (7) DeleteAllMessages
## Request
| Type | Name |
| --- | --- |
| [MessageRecipient](#messagerecipient-structure) | recipient |

## Response
| Type | Name |
| --- | --- |
| Uint32 | uiNbDeletedMessages |

# Types
## MessageRecipient ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | m_uiRecipientType |
| [PID] | m_principalId |
| Uint32 | m_gatheringId |

## UserMessage ([Structure])
| This structure inherits from [Data] |
| --- |

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
| [MessageRecipient](#messagerecipient-structure) | m_messageRecipient |

## TextMessage ([Structure])
| This structure inherits from [UserMessage](#usermessage-structure) |
| --- |

| Type | Name |
| --- | --- |
| [String] | m_strTextBody |

## BinaryMessage ([Structure])
| This structure inherits from [UserMessage](#usermessage-structure) |
| --- |

| Type | Name |
| --- | --- |
| [qBuffer] | m_binaryBody |

[String]: NEX-Common-Types.md#string
[qBuffer]: NEX-Common-Types.md#qbuffer
[DateTime]: NEX-Common-Types.md#datetime
[Data]: NEX-Common-Types.md#anydataholder
[List]: NEX-Common-Types.md#list
[PID]: NEX-Common-Types.md#pid
[ResultRange]: NEX-Common-Types.md#resultrange-structure
[Structure]: NEX-Common-Types.md#structure
[Data]: NEX-Common-Types.md#data