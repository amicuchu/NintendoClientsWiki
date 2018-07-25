[[PIA Protocols]] > Station Protocol (0x100)
---

| Protocol Port | Description |
| --- | --- |
| 0 | Unreliable |
| 1 | Reliable |

| Message Type | Description |
| --- | --- |
| 1 | [Connection request](#connection-request) |
| 2 | [Connection response](#connection-response) |
| 3 | [Disconnection request](#disconnection-request) |
| 4 | [Disconenction response](#disconnection-response) |
| 5 | [Ack](#ack) |
| 6 | [Relay connection request](#relay-connection-request) |
| 7 | [Relay connection response](#relay-connection-response) |

# Connection request
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Message type |
| 0x1 | 1 | Connection id |
| 0x2 | 1 | Version maybe? |
| 0x3 | 1 | Is inverse connection request |
| 0x4 | 54 | [StationConnectionInfo](#stationconnectioninfo) |
| 0x3A | 4 | Ack id |

# Connection response
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Message type |
| 0x1 | 1 | Result |
| 0x2 | 1 | Always 3? |
| 0x3 | 1 | Always 3? |

Only present if result is OK:

| Offset | Size | Description |
| --- | --- | --- |
| 0x4 | 66 | [IdentificationInfo](#identificationinfo) |
| 0x46 | 4 | Ack id |

## Connection result
| Value | Description |
| --- | --- |
| 0 | OK |
| 1 | Connection denied |
| 2 | Connection denied |

# Disconnection request
# Disconnection response
# Ack
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Message type |
| 0x1 | 3 | Padding |
| 0x4 | 4 | Ack id |

# Relay connection request
# Relay connection response

# IdentificationInfo
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 32 | Identification (ascii) |
| 0x20 | 32 | Name (utf16-be) |
| 0x40 | 1 | Name length |
| 0x41 | 1 | Always 0? |

# StationConnectionInfo
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 27 | Public [StationLocation](#stationlocation) |
| 0x1B | 27 | Local [StationLocation](#stationlocation) |

# StationLocation
These fields are directly taken from a [StationURL](NEX-Common-Types#station-url).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 8 | [StationAddress](#stationaddress) |
| 0x8 | 4 | PID |
| 0xC | 4 | CID |
| 0x10 | 4 | RVCID |
| 0x14 | 1 | Url type (1=prudp 2=prudps 3=udp) |
| 0x15 | 1 | sid |
| 0x16 | 1 | stream |
| 0x17 | 1 | natm |
| 0x18 | 1 | natf |
| 0x19 | 1 | type |
| 0x1A | 1 | probeinit |

# StationAddress
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 6 | [InetAddress](#inetaddress) |
| 0x6 | 2 | Extension id |

# InetAddress
| Offset | Size | Description |
| --- | -- | --- |
| 0x0 | 4 | Address |
| 0x4 | 2 | Port |