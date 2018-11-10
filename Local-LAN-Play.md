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
| 0x0 | | LanSessionInfo |