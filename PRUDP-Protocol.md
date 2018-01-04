PRUDP is a transport layer protocol on top of UDP whose purpose is to achieve reliability, and optionally encryption and compression. There are two version of this protocol ([V0](#v0-format) and [V1](#v1-format)), but these are pretty similar. The only difference lies in the way the packets are encoded. All values are encoded in little endian byte order

## V0 Format
This format is only used by the friends server, and possibly some 3DS games.

### Packet Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Source port |
| 0x1 | 1 | Destination port |
| 0x2 | 2 | Type and flags |
| 0x4 | 1 | Session id |
| 0x5 | 4 | Packet signature |
| 0x9 | 2 | Sequence id |

Packet-specific data:

| Only present if | Size | Description |
| --- | --- | --- |
| Type is SYN or CONNECT | 4 | Connection signature |
| Type is DATA | 1 | Fragment id |
| Flags & FLAG_HAS_SIZE | 2 | Payload size |

### Payload
The header is followed by the payload with a 1-byte checksum appended to it. The checksum is calculated over the whole packet (both header and encrypted payload), and uses the following algorithm (the example code is written in python):
```python
def calc_checksum(checksum, data):
	#Little endian!
	words = struct.unpack_from("<" + "I" * (len(data) // 4), data)
	temp = sum(words) & 0xFFFFFFFF #32-bit
	
	#Add the sum of the remaining bytes to the checksum
	checksum += sum(data[-(len(data) & 3):])
	
	#And the sum of the bytes of the temporary checksum
	checksum += sum(struct.pack("<I", temp))
	
	return checksum & 0xFF #8-bit checksum
	
checksum = calc_checksum(sum(ACCESS_KEY), packet_data)
```

## V1 Format
This format is used by all Wii U games and apps, except for friends services, and possibly some 3DS games.

| Size | Description |
| --- | --- |
| 2 | Magic number: 0xEA 0xD0 |
| 12 | Packet header |
| 16 | Packet signature |
| | Packet-specific data |
| | Payload |

### Packet Header
| Offset | Size | Description |
| --- | --- | --- |
| 0x2 | 1 | PRUDP version (always 1) |
| 0x3 | 1 | Length of packet-specific data |
| 0x4 | 2 | Payload size |
| 0x6 | 1 | Source port |
| 0x7 | 1 | Destination port |
| 0x8 | 2 | Type and flags |
| 0xA | 1 | Session id |
| 0xB | 1 | Always 0 |
| 0xC | 2 | Sequence id |

### Packet-Specific Data:
| Only present if | Size | Description |
| --- | --- | --- |
| Type is SYN or CONNECT | 2 | 0x00 0x04 |
| Type is SYN or CONNECT | 4 | Supported functions |
| Type is SYN or CONNECT | 2 | 0x01 0x10 |
| Type is SYN or CONNECT | 16 | Connection signature |
| Type is CONNECT | 2 | 0x03 0x02 |
| Type is CONNECT | 2 | Unknown, random integer |
| Type is SYN or CONNECT | 4 | 0x04 0x01 0x00 |
| Type is DATA | 2 | 0x02 0x01 |
| Type is DATA | 1 | Fragment id |