After a connection between the consoles has been established, the [PIA protocol](PIA-Protocol) will be used for further communication.

## Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Packet type |
| 0x1 | 4 | Packet size (including header) |

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