## [[NEX Protocols]] > Nintendo Notifications (0x64)

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
| Type | Name |
| --- | --- |
| Uint32 | m_uiType |
| [PID] | m_pidSender |
| [Data] | m_dataholder |

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

[Data]: NEX-Common-Types#any-data-holder
[PID]: NEX-Common-Types#pid
[Structure]: NEX-Common-Types#structure
[String]: NEX-Common-Types#string