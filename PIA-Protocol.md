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
| 0x8 | 2 | Milliseconds since start of session |
| 0xA | 2 | RTT related |

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