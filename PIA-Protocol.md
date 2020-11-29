These packets are sent directly from one console to another, with no server in between. Everything is encoded in big-endian byte order.

All packets consist of an unencrypted [header](#header), which is followed by one or more [messages](#messages), and sometimes a [packet signature](#encryption).

## Header
*Up to 5.3:*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number: `32 AB 98 64` |
| 0x4 | 1 | Encrypted (1=No 2=Yes) |
| 0x5 | 1 | [Connection id](#connection-id) |
| 0x6 | 2 | [Packet id](#packet-id) |
| 0x8 | 2 | [Session timer](#rtt-calculation) |
| 0xA | 2 | [RTT timer](#rtt-calculation) |

*5.7 - 5.10:*

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

*5.11 - 5.19:*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number: `32 AB 98 64` |
| 0x4 | 1 | This byte consists of two parts:<br>`0x80`: Encryption enabled<br>`0x7F`: Version number |
| 0x5 | 1 | [Connection id](#connection-id) |
| 0x6 | 2 | [Packet id](#packet-id) |
| 0x8 | 8 | [AES-GCM nonce](#encryption) |
| 0x10 | 16 | [AES-GCM authentication tag](#encryption) |

*5.24:*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number: `32 AB 98 64` |
| 0x4 | 1 | Unknown |
| 0x5 | 1 | Unknown |
| 0x6 | 2 | Unknown |
| 0x10 | 16 | Unknown |

*5.29:*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number: `32 AB 98 64` |
| 0x4 | 1 | This byte consists of two parts:<br>`0x80`: Encryption enabled<br>`0x7F`: Version number (9) |
| 0x5 | 4 | Unknown |
| 0x9 | 4 | Unknown |
| 0xD | 2 | Packet id |
| 0xF | 17 | Unknown |

### Connection ID
During connection establishment, the console that wants to connect to another console must set this field to 1, and the console that answers the connection request must set this field to 0. After a connection has been established both consoles generate a random number between 2 and 255. This will be the connection id in any further packets.

### Packet ID
This should be 0 during connection establishment. After a connection has been established this should be an incrementing number starting at 1.

### RTT Calculation
The session timer contains the number of milliseconds since the start of the session. Every client has its own session timer (they are independent from each other). Aside from its own session timer, every client also keeps track of the session timers of all other clients. When A sends a packet to B the RTT timer is what A belives the session timer of B to be. Hopefully, an example will make this clear:

Let's say the session timer of A is at 234 when A sends a packet to B. It takes 2 milliseconds until the packet arrives at B. B receives 234 from A even though the session timer of A is now at 236. 10 milliseconds later, B sends a packet to A with 244 (234 + 10) in the RTT timer field. Again, it takes 2 milliseconds until the packet arrives at A. At this point, the session timer of A is at 248, but it receives 244 in the RTT timer field, so it knows that it takes 4 milliseconds for a packet to travel back and forth between A and B.

![](https://www.dropbox.com/s/4fbobmcugbbokr3/rtt.png?raw=1)

## Messages
This part of the packet may be [encrypted](#encryption). A packet may contain more than one message  (the number of messages is determined from the size of packet).

All messages are padded such that their size is a multiple of 4 bytes.

*Up to 5.3:*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Message flags](#message-flags) |
| 0x1 | 1 | [Source station index](#station-index) |
| 0x2 | 2 | Payload size |
| 0x4 | 4 | [Destination](#destination) |
| 0x8 | 4 | [Source station id](#station-id) |
| 0xC | 2 | [Protocol type](PIA-Protocols.md) |
| 0xE | 2 | Protocol port (protocol-specific) |
| 0x10 | 4 | Reserved (always 0) |
| 0x14 | | Payload (protocol-specific) |
| | | Padding |

*5.9 and 5.10:*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Message flags](#message-flags) |
| 0x1 | 2 | Payload size |
| 0x3 | 8 | [Destination](#destination) |
| 0xB | 8 | [Source station id](#station-id) |
| 0x13 | 1 | [Protocol type](PIA-Protocols.md) |
| 0x14 | 1 | Protocol port (protocol-specific) |
| 0x15 | 3 | Padding (always 0) |
| 0x18 | | Payload (protocol-specific) |
| | | Padding |

*5.11:*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Message flags](#message-flags) |
| 0x1 | 1 | Version (always 1) |
| 0x2 | 2 | Payload size |
| 0x4 | 1 | [Protocol type](PIA-Protocols.md) |
| 0x5 | 1 | Protocol port (protocol-specific) |
| 0x6 | 8 | [Destination](#destination) |
| 0xE | 8 | [Source station id](#station-id) |
| 0x16 | | Payload (protocol-specific) |
| | | Padding |

*5.14 - 5.17:*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Message flags](#message-flags) |
| 0x1 | 1 | Version (always 2) |
| 0x2 | 2 | Payload size |
| 0x4 | 1 | [Protocol type](PIA-Protocols.md) |
| 0x5 | 3 | Protocol port (protocol-specific) |
| 0x8 | 8 | [Destination](#destination) |
| 0x10 | 8 | [Source station id](#station-id) |
| 0x18 | | Payload (protocol-specific) |
| | | Padding |

*5.18:*

Fields that are not present are copied from the previous message.

| Type | Description |
| --- | --- |
| Uint8 | Flags indicating which of the following fields are present. |
| Uint8 | [Message flags](#message-flags). *Only present if `flags & 1`.* |
| Uint16 | Payload size. *Only present if `flags & 2`.* |
| Uint8 | [Protocol type](PIA-Protocols.md). *Only present if `flags & 4`.* |
| Uint24 | Protocol port (protocol-specific). *Only present if `flags & 4`.* |
| Uint64 | [Destination](#destination). *Only present if `flags & 8`.* |
| Uint64 | [Source station id](#station-id). *Only present if `flags & 16`.* |
| Bytes | Payload (protocol-specific) |
| | Padding |

### Message flags
| Mask | Description |
| --- | --- |
| 0x1 | Determines what's stored in the [destination](#destination) field |
| 0x2 | This packet is supposed to be relayed to another console |
| 0x4 | This packet was relayed through another console |
| 0x8 | Unknown |
| 0x10 | The message payload is zlib-compressed |

### Station index
Every console in a mesh gets its own station index. Consoles that haven't joined a mesh yet have this field set to 0xFD. This is not the same as the [station id](#station-id).

### Station id
This is a unique id per station. In NEX mode, it is the principal id (pid). In LDN and LAN mode, it is generated based on the local address of the station.

### Destination
The content of this field depends on the [message flags](#message-flags). If the flag is cleared, this field contains the [station id](#station-id) of the destination console. If the flag is set, this field contains a bitmap where each bit represents one destination console (the bit number of a console is its station index: `1 << station_index`).

## Encryption
Packets are encrypted and signed with the session key.

| Mode | Session key |
| --- | --- |
| NEX | Obtained from server during [matchmaking](Match-Making-Types.md#matchmakesession-structure) |
| LDN | ? |
| LAN | First 16 bytes of the HMAC-SHA256 of the slightly modified [session param](LAN-Protocol.md#lansessioninfo) (the last byte is incremented by 1), with the same game-specific key that's used for the [crypto challenge](LAN-Protocol.md#crypto-challenge). |

**Wii U and Switch (up to 5.3):**

If encryption is enabled, the [messages](#messages) are encrypted with AES-ECB. The packet signature is the HMAC of the whole packet (including the [header](#header)). The packet signature is always present, even if encryption is disabled.

**Switch (5.9 and later):**

If encryption is enabled, the [messages](#messages) are encrypted with AES-GCM. The messages are padded with 0xFF before encryption such that their combined size is a multiple of 16 bytes. The authentication tag is stored in the [header](#header). No other signature is appended to the packet.

The nonce depends on the network type and is generated as follows:

*NEX:*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Connection id](#header) |
| 0x1 | 3 | `gathering_id & 0xFFFFFF` |
| 0x4 | 8 | Nonce from [header](#header) |

*LDN:*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 3 | Some kind of crc32? |
| 0x3 | 1 | [Connection id](#header) |
| 0x4 | 8 | Nonce from [header](#header) |

*LAN:*

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | IP address of source |
| 0x4 | 1 | [Connection id](#header) |
| 0x5 | 7 | Last 7 bytes of nonce from [header](#header) |