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
| 0x4 | 1 | Encrypted (1=No, 2=Yes) |
| 0x5 | 1 | Session id |
| 0x6 | 2 | Packet id |
| 0x8 | 2 | [Session timer](#rtt-calculation) |
| 0xA | 2 | [RTT timer](#rtt-calculation) |

### RTT Calculation
The session timer is the number of milliseconds since the start of the session. Every client has its own session timer (they are independent of each other). Aside from its own session timer, every client also keeps track of the session timers of all other clients. This is quite difficult to explain. Basically, when A sends a packet to B the RTT timer is what A belives the session timer of B to be. Hopefully, an example will make this clear:

Let's say the session timer of A is at 234 when A sends a packet to B. It takes 2 milliseconds until the packet arrives at B. B receives 234 from A even though the session timer of A is now at 236. 10 milliseconds later, B sends a packet to A with 244 (234 + 10) in the RTT timer field. Again, it takes 2 milliseconds until the packet arrives at A. At this point, the session timer of A is at 248, but it receives 244 in the RTT timer field, so it knows that it takes 4 milliseconds for a packet to travel back and forth between A and B.

![](https://www.dropbox.com/s/4fbobmcugbbokr3/rtt.png?raw=1)

## Content
This data may be encrypted (probably AES).

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Flags |
| 0x1 | 1 | Station index |
| 0x2 | 2 | Payload size |
| 0x4 | 4 | Destination |
| 0x8 | 4 | Connection id |
| 0xC | 2 | Protocol id |
| 0xE | 2 | Message id |
| 0x10 | 4 | Unknown (always 0?) |
| 0x14 | | Payload |
| | 16 | HMAC checksum |