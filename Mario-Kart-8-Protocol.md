All packets are sent through the [unreliable protocol](PIA-Protocols).

Every packet consists of one or more records, terminated by a record with type 0xFF.

## Record Header
| Offset | Type | Description |
| --- | --- | --- |
| 0x0 | Uint8 | Type |
| 0x1 | Uint16 | Size |

| Record type | Description |
| --- | --- |
| 0 | [Track selection related](#record-type-0) |
| 1 | Unknown |
| 2 | [Course roulette related](#record-type-2) |
| 3 | Unknown |
| 4 | Unknown |
| 6 | Unknown |
| 7 | Unknown |
| 9 | [Unknown](#record-type-9) |
| 10 | Chat related |
| 0xFD | [Unknown](#record-type-0xfd) |
| 0xFE | [Unknown](#record-type-0xfe) |
| 0xFF | End record |

## Record Type 0
| Offset | Type | Description |
| --- | --- | --- |
| 0x0 | [PlayerInfo](#playerinfo) (x12) | Players |
| 0x90 | [PlayerId](#playerid) | Unknown |
| 0x98 | Uint32 | Flags |
| 0x9C | --- | End of record |

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
| 0x160 | --- | End of record |

## Record Type 9
| Offset | Type | Description |
| --- | --- | --- |
| 0x0 | Uint8 | Unknown |
| 0x1 | --- | End of record |

## Record Type 0xFD
| Offset | Type | Description |
| --- | --- | --- |
| 0x0 | Uint32 | Unknown |
| 0x4 | --- | End of record |

## Record Type 0xFE
| Offset | Type | Description |
| --- | --- | --- |
| 0x0 | Uint32 | Unknown |
| 0x4 | Uint32 | Unknown |
| 0x8 | Uint32 | Unknown |
| 0xC | Uint32 | Unknown |
| 0x10 | Uint32 | Unknown |
| 0x14 | Uint32 | Unknown |
| 0x18 | Uint32 | User id (pid) |
| 0x1C | Uint32 | Unknown |
| 0x20 | Uint8 | Unknown |
| 0x21 | Unk (8 * 27) | Unknown |
| 0xF9 | Unk (8 * 10) | Unknown |
| 0x149 | Uint8 | Unknown |
| 0x14A | Uint8 (x14) | Unknown |
| 0x158 | --- | End of record |

## PlayerId
| Offset | Type | Description |
| --- | --- | --- |
| 0x0 | Uint32 | Station index |
| 0x4 | Unk (4) | Unknown |

## PlayerInfo
| Offset | Type | Description |
| --- | --- | --- |
| 0x0 | Uint32 | Station index |
| 0x4 | Unk (4) | Unknown |
| 0x8 | Unk (4) | Unknown |