All packets are sent through the [unreliable protocol](PIA-Protocols).

Every packet consists of one or more records, terminated by a record with type 0xFF.

## Record Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Type |
| 0x1 | 2 | Size |