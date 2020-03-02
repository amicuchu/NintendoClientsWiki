## [[NEX Protocols]] > Nintendo Notifications (0x64)

Method 2 is only implemented by the friend server and client. There is no known difference between them, except that the server sends some events through method 1 and others through method 2. The client treats them exactly the same.

| Method ID | Method Name |
| --- | --- |
| 1 | [ProcessNintendoNotificationEvent](#processnintendonotificationevent) |
| 2 | [ProcessNintendoNotificationEvent](#processnintendonotificationevent) |

# ProcessNintendoNotificationEvent
## Request
| Type | Description |
| --- | --- |
| [NintendoNotificationEvent](#nintendonotificationevent-structure) | Event object |

## Response
This method does not return anything.

# Types
## NintendoNotificationEvent ([Structure])
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | m_uiType | [Event type](#friend-events) |
| [PID] | m_pidSender | Pid of the user that triggered the notification event |
| [Data] | m_dataholder | Information about the event (depends on the event type) |

## NintendoNotificationEventGeneral ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | m_u32Param |
| Uint64 | m_u64Param1 |
| Uint64 | m_u64Param2 |
| [String] | m_strParam |

## NintendoNotificationEventProfile ([Structure])
| Type | Name |
| --- | --- |
| Uint8 | m_region |
| Uint8 | m_country |
| Uint8 | m_area |
| Uint8 | m_language |
| Uint8 | m_platform |

[Data]: NEX-Common-Types#anydataholder
[PID]: NEX-Common-Types#pid
[Structure]: NEX-Common-Types#structure
[String]: NEX-Common-Types#string