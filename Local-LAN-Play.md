After a connection between the consoles has been established, the [PIA protocol](PIA-Protocol) will be used for further communication.

## Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Packet type |
| 0x1 | 4 | Payload size |
| 0x5 | | Packet payload |

### Packet types
| Value | Description |
| --- | --- |
| 0 | Browse request |
| 1 | Browse reply |
| 2 | Get host request |
| 3 | Get host reply |
| 4 | Get session request |
| 5 | Get session reply |
| 6 | Keep alive message |

## Browse Request
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x23A | [LanSessionSearchCriteria](#lansessionsearchcriteria) |

### LanSessionSearchCriteria
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Unknown |
| 0x2 | 2 | Unknown |
| 0x4 | 2 | Unknown |
| 0x6 | 2 | Unknown |
| 0x8 | 1 | Unknown |
| 0x9 | 1 | Unknown |
| 0xA | 4 | Unknown |
| 0xE | 4 | Unknown |
| 0x12 | 4 | Unknown |
| 0x16 | 4 | Unknown |
| 0x1A | 0x50 | Unknown |
| 0x6A | 0x50 | Unknown |
| 0xBA | 0x50 | Unknown |
| 0x10A | 0x50 | Unknown |
| 0x15A | 0x50 | Unknown |
| 0x1AA | 0x50 | Unknown |
| 0x1FA | 1 | Unknown |
| 0x1FB | 1 | Unknown |
| 0x1FC | 1 | Unknown |
| 0x1FD | 1 | Unknown |
| 0x1FE | 1 | Unknown |
| 0x1FF | 1 | Unknown |
| 0x200 | 4 | Unknown |
| 0x204 | 4 | Unknown |
| 0x208 | 4 | Unknown |
| 0x20C | 4 | Unknown |
| 0x210 | 4 | Unknown |
| 0x214 | 4 | Unknown |
| 0x218 | 4 | Unknown |
| 0x21C | 4 | Unknown |
| 0x220 | 4 | Unknown |
| 0x224 | 4 | Unknown |
| 0x228 | 4 | Unknown |
| 0x22C | 4 | Unknown |
| 0x230 | 1 | Unknown |
| 0x231 | 1 | Unknown |
| 0x232 | 1 | Unknown |
| 0x233 | 1 | Unknown |
| 0x234 | 1 | Unknown |
| 0x235 | 1 | Unknown |
| 0x236 | 4 | Unknown |