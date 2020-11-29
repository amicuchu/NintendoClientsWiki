[PIA Protocols](PIA-Protocols.md) > Reliable Protocol
---

This protocol may be used by games to send data packets to other consoles. The reliable protocol ensures that all packets arrive in the correct order by using sequence ids and acknowledgement.

The payload contains the following data:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Unknown |
| 0x1 | 1 | Unknown |
| 0x2 | 2 | Game data size |
| 0x4 | 2 | Sequence id |
| 0x6 | 2 | Unknown |
| 0x8 | 1 | N |
| 0x9 | 8 * N | Unknown |
| | | Game data |