[[PIA Protocols]] > Mesh Protocol
---

| Protocol Port | Description |
| --- | --- |
| 0 | Unreliable |
| 1 | Reliable |

| Message Type | Description |
| --- | --- |
| 0x01 | [Join request](#join-request) |
| 0x02 | [Join response](#join-response-success) |
| 0x04 | [Leave request](#leave-request) |
| 0x08 | [Leave response](#leave-response) |
| 0x10 | [Destroy mesh](#destroy-request) |
| 0x11 | [Destroy response](#destroy-response) |
| 0x20 | [Update mesh](#update-mesh) |
| 0x21 | Kickout notice |
| 0x22 | Dummy message |
| 0x24 | Connection failure notice |
| 0x40 | Greeting |
| 0x41 | Migration finish |
| 0x42 | Greeting response |
| 0x44 | Migration start |
| 0x48 | Migration response |
| 0x49 | Multi migration start |
| 0x4A | Multi migration rank decision |
| 0x80 | Connection report |
| 0x81 | Relay route directions |

# Join request
*Wii U and Switch (up to 5.10):*

| Type | Description |
| --- | --- |
| Uint8 | Message type (1) |
| Uint8 | Station index |
| Uint16 | Padding (always 0) |
| [StationAddress] | Station address |
| Uint32 | Ack id |

*Switch (5.11 and later):*

| Type | Description |
| --- | --- |
| Uint8 | Message type (1) |
| Uint8 | Station index |
| Uint32 | Ack id |

# Join response (success)
If the join response is too big to be sent in a single packet it is split into fragments.

| Type | Description |
| --- | --- |
| Uint8 | Message type (2) |
| Uint8 | Number of stations in mesh |
| Uint8 | Index of host station |
| Uint8 | Index of joining station |
| Uint8 | Number of fragments |
| Uint8 | Fragment index |
| Uint8 | Number of station info entries in current fragment (N) |
| Uint8 | Base index of station info in current fragment |
| | Version-dependent data |
| [StationInfo] (xN) | Station info list. Each entry is padded such that its size is a multiple of 4 bytes. |
| Uint32 | Ack id |

*Wii U (up to 3.10):* No additional data

*Wii U (4.8 and later):*

| Type | Description |
| --- | --- |
| Uint8 | Maximum number of stations in first mesh |
| Uint8 | Maximum number of stations in second mesh |
| Uint16 | Padding |

*Switch:*

| Type | Description |
| --- | --- |
| Uint8 | Maximum number of stations in first mesh |
| Uint8 | Maximum number of stations in second mesh |
| Uint8 | Maximum number of stations (total) |
| Uint8 | Padding |
| Uint32 | Update counter (incremented on each mesh update) |

# Join response (denying)
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Message type (2) |
| 0x1 | 1 | Always 0 |
| 0x2 | 1 | Always 0xFF |
| 0x3 | 1 | Always 0xFF |
| 0x4 | 1 | Reason |

# Leave request
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Message type |
| 0x1 | 1 | Station index |
| 0x2 | 2 | Padding |
| 0x4 | 8 | [StationAddress] |

# Leave response
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Message type |
| 0x1 | 1 | Station index |
| 0x2 | 2 | Padding |
| 0x4 | 8 | [StationAddress] |

# Destroy request
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Message type |
| 0x1 | 1 | Station index |
| 0x2 | 2 | Padding |
| 0x4 | 8 | [StationAddress] |

# Destroy response
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Message type |
| 0x1 | 1 | Station index |

# Update mesh
Because this message is sent through the reliable mesh protocol it does not need to be split into fragments like the join response.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Message type |
| 0x1 | 1 | Number of stations |
| 0x2 | 1 | Host index |
| 0x3 | 1 | Always 0 |
| 0x4 | 4 | Update counter (incremented on each mesh update) |
| 0x8 | 1 | Always 1 |
| 0x9 | 1 | Always 0 |
| 0xA | 1 | Host index |
| 0xB | 1 | Always 0 |
| 0xC | | [StationInfo] entries |

[StationAddress]: PIA-Types#stationaddress
[StationInfo]: PIA-Types#stationinfo