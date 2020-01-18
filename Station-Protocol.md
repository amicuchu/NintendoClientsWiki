[[PIA Protocols]] > Station Protocol
---

| Protocol Port | Description |
| --- | --- |
| 0 | Unreliable |
| 1 | Reliable |

| Message Type | Description |
| --- | --- |
| 1 | [Connection request](#connection-request) |
| 2 | [Connection response (denying)](#connection-response-denying)<br>[Connection response (accepted)](#connection-response-accepted) |
| 3 | [Disconnection request](#disconnection-request) |
| 4 | [Disconnection response](#disconnection-response) |
| 5 | [Ack](#ack) |
| 6 | Relay connection request |
| 7 | Relay connection response |

Version numbers for [connection request](#connection-request) and [response](#connection-response):

| Version | PIA Version |
| --- | --- |
| 2 | 3.6 |
| 3 | 3.9 - 3.10 |
| 5 | 4.8 - 4.10 |
| 7 | 5.2 - 5.3 |
| 8 | 5.9 |
| 9 | 5.10 - 5.18 |

# Connection request
| Type | Description |
| --- | --- |
| Uint8 | Message type  (1) |
| Uint8 | Connection id |
| Uint8 | Version |
| Uint8 | Is inverse connection request |
| Bytes | Version-dependent data |
| Uint32 | Ack id |

*Version 2 - 5:*

| Type | Description |
| --- | --- |
| [StationConnectionInfo] | Station connection info |

*Version 7:*

| Type | Description |
| --- | --- |
| Uint64 | NEX principal id (pid) |
| [StationConnectionInfo] | Station connection info |

*Version 8:*

| Type | Description |
| --- | --- |
| Uint64 | NEX principal id (pid) |
| Uint32 | NEX connection id (cid) |
| Uint8 | Inverse connection id |
| [StationConnectionInfo] | Station connection info |

*Version 9:*

| Type | Description |
| --- | --- |
| Uint64 | NEX principal id (pid) |
| Uint32 | NEX connection id (cid) |
| Uint8 | Inverse connection id |
| [StationLocation] | Station location |

# Connection response (denying)

| Type | Description |
| --- | --- |
| Uint8 | Message type (2) |
| Uint8 | [Reason](#connection-result) |
| Uint8 | Version |
| Uint8 | Always 0 |

*Only present in version 8 and 9:*

| Type | Description |
| --- | --- |
| Uint8 | Always 0 |
| Uint64 | NEX principal id (pid) |
| Uint32 | NEX connection id (cid) |

### Connection result
| Value | Description |
| --- | --- |
| 1 | Connection denied |
| 2 | Incompatible version |

# Connection response (accepted)

| Type | Description |
| --- | --- |
| Uint8 | Message type (2) |
| Uint8 | [Result](#connection-result) |
| Uint8 | Version |
| Uint8 | Always 3 on Wii U, and 4 on Switch. |
| | Version-dependent data |
| Uint32 | Ack id. *Only present if the connection request was accepted.* |

*Version 2 - 5:*

| Type | Description |
| --- | --- |
| Uint8[32] | Identification token (ascii) |
| Uint16[32] | Name (utf16-be) |
| Uint8 | Name length |
| Uint8 | Unknown |

*Version 8 and 9:*

| Type | Description |
| --- | --- |
| Uint8 | Unknown |
| Uint64 | NEX principal id (pid) |
| Uint32 | NEX connection id (cid) |

# Disconnection request
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Message type |

# Disconnection response
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Message type |

# Ack
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Message type |
| 0x1 | 3 | Padding |
| 0x4 | 4 | Ack id |

[StationConnectionInfo]: PIA-Types#stationconnectioninfo
[StationLocation]: PIA-Types#stationlocation
[IdentificationInfo]: PIA-Types#identificationinfo