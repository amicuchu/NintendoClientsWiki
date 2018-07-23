These packets are sent directly from one console to another, with no server in between.

## Packet format
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 12 | [Header](#header) |
| 0xC | | [Content](#content) |

## Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number: 32 AB 98 64 |
| 0x4 | 1 | Encrypted (1=No 2=Yes) |
| 0x5 | 1 | [Connection id](#connection-id) |
| 0x6 | 2 | [Packet id](#packet-id) |
| 0x8 | 2 | [Session timer](#rtt-calculation) |
| 0xA | 2 | [RTT timer](#rtt-calculation) |

### Connection ID
During connection establishment, the console that wants to connect to another console must set this field to 1, and the console that answers the connection request must set this field to 0. After a connection has been established both console generate a random number between 2 and 255. This will be the connection id in any further packets.

### Packet ID
This should be 0 during connection establishment. After a connection has been established this should be an incrementing number starting at 1.

### RTT Calculation
The session timer is the number of milliseconds since the start of the session. Every client has its own session timer (they are independent of each other). Aside from its own session timer, every client also keeps track of the session timers of all other clients. This is quite difficult to explain. Basically, when A sends a packet to B the RTT timer is what A belives the session timer of B to be. Hopefully, an example will make this clear:

Let's say the session timer of A is at 234 when A sends a packet to B. It takes 2 milliseconds until the packet arrives at B. B receives 234 from A even though the session timer of A is now at 236. 10 milliseconds later, B sends a packet to A with 244 (234 + 10) in the RTT timer field. Again, it takes 2 milliseconds until the packet arrives at A. At this point, the session timer of A is at 248, but it receives 244 in the RTT timer field, so it knows that it takes 4 milliseconds for a packet to travel back and forth between A and B.

![](https://www.dropbox.com/s/4fbobmcugbbokr3/rtt.png?raw=1)

## Content
If encryption is enabled, this data is encrypted with AES.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Flags](#flags) |
| 0x1 | 1 | [Station index](#station-index) |
| 0x2 | 2 | Payload size |
| 0x4 | 4 | [Destination mask](#destination-mask) |
| 0x8 | 4 | [Source station key](#station-key) |
| 0xC | 2 | [Protocol id](PIA-Protocols) |
| 0xE | 2 | Message type (protocol-specific) |
| 0x10 | 4 | Reserved (always 0) |
| 0x14 | | Payload |
| | | Padding to align checksum to 4 bytes |
| | 16 | [HMAC checksum](#signature) |

### Flags
| Value | Description |
| --- | --- |
| 1 | Unknown. This packet is sent to one console. The destination field contains only the station mask of the receiving console. |
| 2 | Unknown. This packet may be sent to multiple consoles. The destination field contains the station masks of all receiving consoles. |
| 4 | Unknown |
| 8 | Unknown |

### Station index
Every connected console gets a unique station index. This field is set to 0xFD until a connection has been established with at least one other console.

### Destination mask
A station mask is calculated as follows: `1 << station_index`. The destination mask is the station mask of every destination console ORed together.

### Station key
The station key of a console is its Rendez-Vous connection id. This is the connection id returned by [SecureProtocol.Register](Secure-Protocol#1-register) or [SecureProtocol.RegisterEx](Secure-Protocol#4-registerex).

### Signature
A HMAC checksum of the whole packet (including the header) is added to the packet before it's encrypted. The key is the session key obtained from the [match making service](Matchmake-Extension-Protocol).