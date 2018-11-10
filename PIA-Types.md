[[PIA Protocols]] > Types
---

| Table of Contents |
| --- |
| [IdentificationInfo](#identificationinfo) |
| [StationInfo](#stationinfo) |
| [StationConnectionInfo](#stationconnectioninfo) |
| [StationLocation](#stationlocation) |
| [StationAddress](#stationaddress) |
| [InetAddress](#inetaddress) |

## IdentificationInfo
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 32 | Identification (ascii) |
| 0x20 | 32 | Name (utf16-be) |
| 0x40 | 1 | Name length |
| 0x41 | 1 | Always 0? |

## StationInfo
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x36 | [StationConnectionInfo](#stationconnectioninfo) |
| 0x36 | 1 | Station index |
| 0x37 | 1 | Padding |

## StationConnectionInfo
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 27 | Public [StationLocation](#stationlocation) |
| 0x1B | 27 | Local [StationLocation](#stationlocation) |

## StationLocation
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

## StationAddress
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 6 | [InetAddress](#inetaddress) |

Only present in some games:

| Offset | Size | Description |
| --- | --- | --- |
| 0x6 | 2 | Extension id |

## InetAddress
| Offset | Size | Description |
| --- | -- | --- |
| 0x0 | 4 | Address |
| 0x4 | 2 | Port |