These packets are sent directly from one console to another, with no server in between. Everything is encoded in big-endian byte order.

All packets consist of an unencrypted [header](#header), which is followed by one or more [payloads](#payload), and sometimes a [packet signature](#encryption).

## Header
*Wii U:*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number: `32 AB 98 64` |
| 0x4 | 1 | Encrypted (1=No 2=Yes) |
| 0x5 | 1 | [Connection id](#connection-id) |
| 0x6 | 2 | [Packet id](#packet-id) |
| 0x8 | 2 | [Session timer](#rtt-calculation) |
| 0xA | 2 | [RTT timer](#rtt-calculation) |

*Switch (up to 5.10):*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number: `32 AB 98 64` |
| 0x4 | 1 | Encrypted (1=No 2=Yes) |
| 0x5 | 1 | [Connection id](#connection-id) |
| 0x6 | 2 | [Packet id](#packet-id) |
| 0x8 | 2 | [Session timer](#rtt-calculation) |
| 0xA | 2 | [RTT timer](#rtt-calculation) |
| 0xC | 8 | [AES-GCM nonce](#encryption) |
| 0x14 | 16 | [AES-GCM authentication tag](#encryption) |

*Switch (5.11 and later):*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number: `32 AB 98 64` |
| 0x4 | 1 | This byte consists of two parts:<br>`0x80`: Encryption enabled<br>`0x7F`: Version number |
| 0x5 | 1 | [Connection id](#connection-id) |
| 0x6 | 2 | [Packet id](#packet-id) |
| 0x8 | 8 | [AES-GCM nonce](#encryption) |
| 0x10 | 16 | [AES-GCM authentication tag](#encryption) |

### Connection ID
During connection establishment, the console that wants to connect to another console must set this field to 1, and the console that answers the connection request must set this field to 0. After a connection has been established both consoles generate a random number between 2 and 255. This will be the connection id in any further packets.

### Packet ID
This should be 0 during connection establishment. After a connection has been established this should be an incrementing number starting at 1.

### RTT Calculation
The session timer contains the number of milliseconds since the start of the session. Every client has its own session timer (they are independent from each other). Aside from its own session timer, every client also keeps track of the session timers of all other clients. When A sends a packet to B the RTT timer is what A belives the session timer of B to be. Hopefully, an example will make this clear:

Let's say the session timer of A is at 234 when A sends a packet to B. It takes 2 milliseconds until the packet arrives at B. B receives 234 from A even though the session timer of A is now at 236. 10 milliseconds later, B sends a packet to A with 244 (234 + 10) in the RTT timer field. Again, it takes 2 milliseconds until the packet arrives at A. At this point, the session timer of A is at 248, but it receives 244 in the RTT timer field, so it knows that it takes 4 milliseconds for a packet to travel back and forth between A and B.

![](https://www.dropbox.com/s/4fbobmcugbbokr3/rtt.png?raw=1)

## Payload
This part of the packet may be [encrypted](#encryption). A packet may contain more than one payload (the number of payloads is determined from the size of packet).

All payloads are padded with 0's such that their size is a multiple of 4 bytes.

*Wii U and Switch (up to 5.3):*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Packet flags](#packet-flags) |
| 0x1 | 1 | [Source station index](#station-index) |
| 0x2 | 2 | Payload size |
| 0x4 | 4 | [Destination mask](#destination-mask) |
| 0x8 | 4 | [Source station key](#station-key) |
| 0xC | 2 | [Protocol type](PIA-Protocols) |
| 0xE | 2 | Protocol port (protocol-specific) |
| 0x10 | 4 | Reserved (always 0) |
| 0x14 | | Payload (protocol-specific) |
| | | Padding |

*Switch (5.9 and 5.10):*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Packet flags](#packet-flags) |
| 0x1 | 2 | Payload size |
| 0x3 | 8 | [Destination mask](#destination-mask) |
| 0xB | 8 | [Source station key](#station-key) |
| 0x13 | 1 | [Protocol type](PIA-Protocols) |
| 0x14 | 1 | Protocol port (protocol-specific) |
| 0x15 | 3 | Padding (always 0) |
| 0x18 | | Payload (protocol-specific) |
| | | Padding |

*Switch (5.11):*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Packet flags](#packet-flags) |
| 0x1 | 1 | Version (always 1) |
| 0x2 | 2 | Payload size |
| 0x4 | 1 | [Protocol type](PIA-Protocols) |
| 0x5 | 1 | Protocol port (protocol-specific) |
| 0x6 | 8 | [Destination mask](#destination-mask) |
| 0xE | 8 | [Source station key](#station-key) |
| 0x16 | | Payload (protocol-specific) |
| | | Padding |

*Switch (5.14):*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Packet flags](#packet-flags) |
| 0x1 | 1 | Version (always 2) |
| 0x2 | 2 | Payload size |
| 0x4 | 1 | [Protocol type](PIA-Protocols) |
| 0x5 | 3 | Protocol port (protocol-specific) |
| 0x8 | 8 | [Destination mask](#destination-mask) |
| 0x10 | 8 | [Source station key](#station-key) |
| 0x18 | | Payload (protocol-specific) |
| | | Padding |

*Switch (5.18):*

Fields that are not present are copied from the previous packet.

| Type | Description |
| --- | --- |
| Uint8 | Flags indicating which of the following fields are present. |
| Uint8 | [Packet flags](#packet-flags). *Only present if `flags & 1`.* |
| Uint16 | Payload size. *Only present if `flags & 2`.* |
| Uint8 | [Protocol type](PIA-Protocols). *Only present if `flags & 4`.* |
| Uint24 | Protocol port (protocol-specific). *Only present if `flags & 4`.* |
| Uint64 | [Destination mask](#destination-mask). *Only present if `flags & 8`.* |
| Uint64 | [Source station key](#station-key). *Only present if `flags & 16`.* |
| Bytes | Payload (protocol-specific) |
| | Padding |

### Packet flags
| Value | Description |
| --- | --- |
| 1 | Unknown. This packet is sent to one console. The destination field contains only the station mask of the receiving console. |
| 2 | Unknown. This packet may be sent to multiple consoles. The destination field contains the station masks of all receiving consoles. |
| 4 | Unknown |
| 8 | Unknown |

### Station index
Every console in a mesh gets its own station index. Consoles that haven't joined a mesh yet have this field set to 0xFD.

### Destination mask
A station mask is calculated as follows: `1 << station_index`. The destination mask is the station mask of every destination console ORed together.

### Station key
This is a unique id per station. In NEX mode, it is the [Rendez-Vous connection id](Secure-Protocol#1-register). In LDN and LAN mode, it is generated based on the local address of the station.

## Encryption
Packets are encrypted and signed with the session key.

| Mode | Session key |
| --- | --- |
| NEX | Obatined from server during [matchmaking](Match-Making-Types#matchmakesession-structure) |
| LDN | ? |
| LAN | First 16 bytes of the HMAC-SHA256 of the slightly modified [session param](LAN-Protocol#lansessioninfo) (the last byte is incremented by 1), with the same game-specific key that's used for the [crypto challenge](LAN-Protocol#crypto-challenge). |

### Wii U
If encryption is enabled, the [payload](#payload) is encrypted with AES-ECB. The packet signature is the HMAC of the whole packet (including the [header](#header)). The packet signature is always present, even if encryption is disabled.

### Switch
If encryption is enabled, the [payload](#payload) is encrypted with AES-GCM. The payload is padded with 0xFF such that its size is a multiple of 16 bytes. The authentication tag is stored in the [header](#header). No other signature is appended to the packet.

The nonce depends on the network type and is generated as follows:

**NEX:**

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Connection id](#header) |
| 0x1 | 3 | `gathering_id & 0xFFFFFF` |
| 0x4 | 8 | Nonce from [header](#header) |

**LDN:**

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 3 | Some kind of crc32? |
| 0x3 | 1 | [Connection id](#header) |
| 0x4 | 8 | Nonce from [header](#header) |

**LAN:**

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | IP address of source |
| 0x4 | 1 | [Connection id](#header) |
| 0x5 | 7 | Last 7 bytes of nonce from [header](#header) |