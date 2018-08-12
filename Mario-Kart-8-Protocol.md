All packets are sent through the [unreliable protocol](PIA-Protocols).

Every packet consists of one or more records, terminated by a record with type 0xFF.

## Record Header
| Offset | Type | Description |
| --- | --- | --- |
| 0x0 | Uint8 | Type |
| 0x1 | Uint16 | Size |

| Record type | Description |
| --- | --- |
| 0 | Unknown |
| 1 | Unknown |
| 2 | [Course roulette related](#record-type-2) |
| 3 | Unknown |
| 4 | Unknown |
| 6 | Unknown |
| 7 | Unknown |
| 9 | Unknown |
| 10 | Unknown |
| 0xFD | Unknown |
| 0xFE | Unknown |

## Record Type 2
| Offset | Type | Description |
| --- | --- | --- |
| 0x0 | Unk (8*12) | Unknown |
| 0x60 | Uint32 (x4) | [Track options](Mario-Kart-8-Track-IDs) |
| 0x70 | Uint32 | Unknown |
| 0x74 | Uint32 | Unknown |
| 0x78 | [PlayerInfo](#playerinfo) (x12) | Players |
| 0x108 | Unk (8*10) | Unknown |
| 0x158 | Uint16 | Unknown |
| 0x15A | Uint16 | Unknown |
| 0x15C | Unk (4) | Unknown |

## PlayerInfo
| Offset | Type | Description |
| --- | --- | --- |
| 0x0 | Uint32 | Station index |
| 0x4 | Unk (4) | Unknown |
| 0x8 | Unk (4) | Unknown |