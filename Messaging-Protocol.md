## [[NEX Protocols]] > Messaging (0x17)

| Method ID | Method Name |
| --- | --- |
| 1 | [DeliverMessage](#1-delivermessage) |
| 2 | GetNumberOfMessages |
| 3 | GetMessageHeaders |
| 4 | RetrieveAllMessagesWithinRange |
| 5 | RetrieveMessages |
| 6 | DeleteMessages |
| 7 | DeleteAllMessages |

# (1) DeliverMessage
## Request
| Type | Name | Description |
| --- | --- | --- |
| [Data] | oUserMessage | Message |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [Data] | oModifiedMessage | |
| [List]&lt;Uint32&gt; | lstSandboxNodeId | |
| [List]&lt;[PID]&gt; | lstParticipants | |

[Data]: NEX-Common-Types#any-data-holder
[List]: NEX-Common-Types#list
[PID]: NEX-Common-Types#pid