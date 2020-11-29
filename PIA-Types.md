[PIA Protocols](PIA-Protocols.md) > Types
---

| Table of Contents |
| --- |
| [StationInfo](#stationinfo) |
| [StationConnectionInfo](#stationconnectioninfo) |
| [StationLocation](#stationlocation) |
| [StationAddress](#stationaddress) |
| [InetAddress](#inetaddress) |

## StationInfo
*Wii U and Switch (up to 5.9):*

| Type | Description |
| --- | --- |
| [StationConnectionInfo](#stationconnectioninfo) | Connection info |
| Uint8 | Station index |
| | Padding such that the size becomes a multiple of 4 bytes. |

*Wii U and Switch (5.10 and later):*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 0x3E | [StationLocation](#stationlocation). If it takes up less than 0x3E bytes the remaining bytes are filled with 0's. |
| 0x3E | 1 | Station index |
| 0x3F | 1 | Padding |

## StationConnectionInfo
| Type | Description |
| --- | --- |
| [StationLocation](#stationlocation) | Public station location |
| [StationLocation](#stationlocation) | Local station location |

## StationLocation
This structure holds fields that are directly taken from a [StationURL](NEX-Common-Types.md#station-url).

*Wii U and Switch (up to 5.9):*

| Type | Description |
| --- | --- |
| [StationAddress](#stationaddress) | Station address |
| [PID](NEX-Common-Types.md#pid) | PID |
| Uint32 | CID |
| Uint32 | RVCID |
| Uint8 | Url type (1=prudp 2=prudps 3=udp) |
| Uint8 | sid |
| Uint8 | stream |
| Uint8 | natm |
| Uint8 | natf |
| Uint8 | type |
| Uint8 | probeinit |
| [InetAddress](#inetaddress) | Relay address. *Only present on Nintendo Switch.* |

*Switch (5.10):*

| Type | Description |
| --- | --- |
| [InetAddress](#inetaddress) | Public address |
| [InetAddress](#inetaddress) | Local address |
| [InetAddress](#inetaddress) | Relay address |
| [PID](NEX-Common-Types.md#pid) | PID |
| Uint32 | CID |
| Uint32 | RVCID |
| Uint8 | `0x3`: natf<br>`0xC`: natm |
| Uint8 | type |
| Uint8 | probeinit |
| Uint8 | Is local |

*Switch (5.11 and later):*

| Type | Description |
| --- | --- |
| Uint8 | Size of public address |
| Uint8 | Size of local address |
| [InetAddress](#inetaddress) | Public address (encoding depends on size) |
| [InetAddress](#inetaddress) | Local address (encoding depends on size) |
| [InetAddress](#inetaddress) | Relay address (old encoding) |
| [PID](NEX-Common-Types.md#pid) | PID |
| Uint32 | CID |
| Uint32 | RVCID |
| Uint8 | `0x3`: natf<br>`0xC`: natm |
| Uint8 | type |
| Uint8 | probeinit |
| Uint8 | Is local |

## StationAddress
| Type | Description |
| --- | --- |
| [InetAddress](#inetaddress) | Address |
| Uint16 | Extension id. *Only present on Wii U.* |

## InetAddress
A new encoding was introduced in PIA 5.11 that's capable of representing IPv6 addresses. Even in games using PIA 5.11 or later, sometimes the old encoding is still used. Which encoding is used depends on the context.

#### Old version
This structure can only represent IPv4 addresses.

| Offset | Size | Description |
| --- | -- | --- |
| 0x0 | 4 | Address |
| 0x4 | 2 | Port |

#### New version
This structure can represent both IPv4 and IPv6 addresses.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 16 | Address |
| 0x10 | 2 | Port |