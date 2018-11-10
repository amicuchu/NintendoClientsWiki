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
| Type | Description |
| --- | --- |
| [StationConnectionInfo](#stationconnectioninfo) | Connection info |
| Uint8 | Station index |
| Uint8 | Padding |

## StationConnectionInfo
| Type | Description |
| --- | --- |
| [StationLocation](#stationlocation) | Public station location |
| [StationLocation](#stationlocation) | Local station location |

## StationLocation
These fields are directly taken from a [StationURL](NEX-Common-Types#station-url).

| Type | Description |
| --- | --- |
| [StationAddress](#stationaddress) | Station address |
| [PID](NEX-Common-Types#pid) | PID |
| Uint32 | CID |
| Uint32 | RVCID |
| Uint8 | Url type (1=prudp 2=prudps 3=udp) |
| Uint8 | sid |
| Uint8 | stream |
| Uint8 | natm |
| Uint8 | natf |
| Uint8 | type |
| Uint8 | probeinit |

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