## [[NEX Protocols]] > Notifications (0x0E)

| Method ID | Method Name |
| --- | --- |
| 1 | ProcessNotificationEvent |

# (1) ProcessNotificationEvent
## Request
| Type | Name | Description |
| --- | --- | --- |
| [NotificationEvent](#notificationevent) | oEvent | Event object |

### NotificationEvent ([Structure])
**Wii U:**

| Type | Name | Description 
| --- | --- | --- |
| [PID] | m_pidSource | Source pid |
| Uint32 | m_uiType | Type |
| Uint32 | m_uiParam1 | Parameter 1 |
| Uint32 | m_uiParam2 | Parameter 2 |
| [String] | m_strParam | String parameter |

**Switch:**
| Type | Name |
| --- | --- |
| [PID] | m_pidSource |
| Uint32 | m_uiType |
| Uint64 | m_uiParam1 |
| Uint64 | m_uiParam2 |
| [String] | m_strParam |
| Uint64 | m_uiParam3 |
| [Map]&lt;[Variant]&gt; | m_mapParam |

## Response
This method does not return anything.

[PID]: NEX-Common-Types#pid
[String]: NEX-Common-Types#string
[Structure]: NEX-Common-Types#structure
[Map]: NEX-Common-Types#map
[Variant]: NEX-Common-Types#variant