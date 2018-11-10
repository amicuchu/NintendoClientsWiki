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
| 0 | [Browse request](#0-browse-request) |
| 1 | [Browse reply](#1-browse-reply) |
| 2 | Get host request |
| 3 | Get host reply |
| 4 | Get session request |
| 5 | Get session reply |
| 6 | Keep alive message |

## (0) Browse Request
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x23A | [LanSessionSearchCriteria](#lansessionsearchcriteria) |

### LanSessionSearchCriteria
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Minimum number of participants ([range](#range)) |
| 0x4 | 4 | Maximum number of participants ([range](#range)) |
| 0x8 | 1 | Opened only |
| 0x9 | 1 | Vacant only |
| 0xA | 4 | Result range offset |
| 0xE | 4 | Result range size |
| 0x12 | 4 | Game mode |
| 0x16 | 4 | Session type |
| 0x1A | 0x50 * 6 | [Attribute lists](#attribute-list) |
| 0x1FA | 1 * 6 | Number of attributes |
| 0x200 | 4 * 6 | Attribute range min |
| 0x218 | 4 * 6 | Attribute range max |
| 0x230 | 1 * 6 | Is attribute range used |
| 0x236 | 4 | [Validity flags](#validity-flags) |

#### Validity flags
These flags indicate which fields have a valid value set.

| Mask | Description |
| --- | --- |
| 0x1 | Minimum number of participants |
| 0x2 | Maximum number of participants |
| 0x4 | Opened only |
| 0x8 | Vacant only |
| 0x10 | Game mode |
| 0x20 | Session type |
| 0x40 | First attribute list |
| ... | ... |
| 0x800 | Last attribute list |

#### Range
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Minimum |
| 0x2 | 2 | Maximum |

#### Attribute list
Each attribute list may contain up to 20 attributes. Every attribute is stored as a 4-byte integer.

## (1) Browse reply
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | | [LanSessionInfo](#lansessioninfo) |

### LanSessionInfo
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Game mode |
| 0x4 | 4 | Session id |
| 0x8 | 4 * 6 | Attributes |
| 0x20 | 2 | Current number of participants |
| 0x22 | 2 | Minimum number of participants |
| 0x24 | 2 | Maximum number of participants |
| 0x26 | 4 | Session type |
| 0x2A | 0x180 | Application data |
| 0x1AA | 4 | Application data size |
| 0x1AE | 1 | Is opened |
| 0x1AF | 0x23 | [StationLocation](PIA-Types#stationlocation) of host |
| 0x1D2 | 0x32 * 16 | [LanStationInfo](#lanstationinfo) for every player in the room |

#### LanStationInfo
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Role |
| 0x1 | 1 | Username encoding type |
| 0x2 | 20 | Username |
| 0x2A | 8 | Station id |
