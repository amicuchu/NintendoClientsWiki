These packets are sent directly from one console to another, with no server in between.

## Packet format
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 12 | [Header](#header) |
| 0xC | | [Content](#content) |
| | 16 | HMAC checksum |

## Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Magic number: 32 AB 98 64 |
| 0x4 | 1 | Encrypted (1=No, 2=Yes) |
| 0x5 | 1 | Session id |
| 0x6 | 2 | Packet id |
| 0x8 | 2 | RTT related |
| 0xA | 2 | RTT related |

## Content
This data may be encrypted.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Unknown |
| 0x2 | 2 | Payload size |
| 0x4 | 4 | Destination |
| 0x8 | 4 | Connection id |
| 0xC | 2 | Service id |
| 0xE | 2 | Method id |
| 0x10 | 4 | Unknown (always 0?) |
| 0x14 | | Payload |