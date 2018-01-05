PRUDP is a transport layer protocol on top of UDP whose aim is to reliably send UDP packets. There are two version of this protocol ([V0](#v0-format) and [V1](#v1-format)), but these are pretty similar. The only difference lies in the way the packets are encoded. All values are encoded in little endian byte order

### Basic operation
When a client connects to a server, it sends a SYN packet. As soon as this packet is acknowledged by the server, it sends a CONNECT packet. When this packet has been acknowledged too, a connection has been made and the client and server can start sending DATA packets. If the client wants to close the connection, it sends a DISCONNECT packet. This packet is acknowledged three times by the server, presumably to ensure the client receives the ACK.

The following techniques are used to achieve this reliability:
* A packet that has FLAG_NEED_ACK set must be acknowledged by the receiver. If the sender doesn't receive an acknowledgement after a certain amount of time it will resend the packet.
* A [sequence id](#sequence-id) is sent along with a packet, so the receiver can reorder packets if necessary.
* Both client and server send PING packets to each other after a certain amount of time has passed.

### Encryption
All packet payloads are encrypted using RC4, with separate streams for client-to-server packets and server-to-client packets. The connection to the authentication server is encrypted using a default key that's always the same: "CD&ML". The connection to the secure server is encrypted using the secure key from the [Kerberos ticket](Kerberos-Authentication#kerberos-ticket).

### Source/destination port
These are "virtual ports", probably to distinguish between connections if a single game/app opens multiple connections at once, although no games actually seem to do this. It's unclear how exactly they're calculated, but normally, the server is identified by 0xA1 and the client by 0xAF.

### Type and flags
This field is made by concatening a 4-bit type value to 12 bits of packet flags. For example, a PING packet with FLAG_RELIABLE and FLAG_NEED_ACK would have this value set to 0x0064 (but remember everything is little endian so it would be stored as 0x64 0x00).

| Mask | Description |
| --- | --- |
| 0x001 | FLAG_ACK: This is an acknowledgement packet |
| 0x002 | FLAG_RELIABLE: This packet is supposed to be reliable |
| 0x004 | FLAG_NEED_ACK: This packet must be acknowledged |
| 0x008 | FLAG_HAS_SIZE: This packet includes its payload size |
| 0x200 | FLAG_MULTI_ACK: This packet acknowledges multiples packets at once. The payload contains information on which packets are acknowledged. |

| Value | Type |
| --- | --- |
| 0 | SYN |
| 1 | CONNECT |
| 2 | DATA |
| 3 | DISCONNECT |
| 4 | PING |

### Session id
This is a random value generated at the start of each session. The server's session id is not necessarily the same as the client's session id.

### Sequence id
This is an incrementing value used to ensure that packets arrive in correct order. The sequence id of client-to-server packets is separate from the sequence id of server-to-client packets.

### Fragment id
Big data packets are split into smaller ones. The fragment ids assigned to packets are counting downwards towards zero. This way the receiver knows how many fragments are left until a full packet has been received. For example, if a message is split into three fragments, the first fragment will have fragment id 2, the second one will have fragment id 1, and the last one fragment id 0.

### Connection signature
The server sends its connection signature in its response to the client's SYN packet. The client sends its connection signature in the CONNECT packet. Other SYN/CONNECT packets have this field set to 0.

If present, the connection signature is the first 4 bytes of a HMAC based on the perceived ip and port of the other end point. However, the key used to calculate this hash seems to be initialized to a random value, thus resulting in an unverifiable hash.

## V0 Format
This format is only used by the friends server, and possibly some 3DS games.

### Packet header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Source port](#sourcedestination-port) |
| 0x1 | 1 | [Destination port](#sourcedestination-port) |
| 0x2 | 2 | [Type and flags](#type-and-flags) |
| 0x4 | 1 | [Session id](#session-id) |
| 0x5 | 4 | Packet signature |
| 0x9 | 2 | [Sequence id](#sequence-id) |

Packet-specific data:

| Only present if | Size | Description |
| --- | --- | --- |
| Type is SYN or CONNECT | 4 | [Connection signature](#connection-signature) |
| Type is DATA | 1 | [Fragment id](#fragment-id) |
| Flags & FLAG_HAS_SIZE | 2 | Payload size |

### Packet signature

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

### Packet header
| Offset | Size | Description |
| --- | --- | --- |
| 0x2 | 1 | PRUDP version (always 1) |
| 0x3 | 1 | Length of packet-specific data |
| 0x4 | 2 | Payload size |
| 0x6 | 1 | [Source port](#sourcedestination-port) |
| 0x7 | 1 | [Destination port](#sourcedestination-port) |
| 0x8 | 2 | [Type and flags](#type-and-flags) |
| 0xA | 1 | [Session id](#session-id) |
| 0xB | 1 | Always 0 |
| 0xC | 2 | [Sequence id](#sequence-id) |

### Packet signature

### Packet-specific data
| Only present if | Size | Description |
| --- | --- | --- |
| Type is SYN or CONNECT | 2 | 0x00 0x04 |
| Type is SYN or CONNECT | 4 | Supported functions (unknown purpose) |
| Type is SYN or CONNECT | 2 | 0x01 0x10 |
| Type is SYN or CONNECT | 16 | [Connection signature](#connection-signature) |
| Type is CONNECT | 2 | 0x03 0x02 |
| Type is CONNECT | 2 | Unknown, random integer |
| Type is SYN or CONNECT | 4 | 0x04 0x01 0x00 |
| Type is DATA | 2 | 0x02 0x01 |
| Type is DATA | 1 | [Fragment id](#fragment-id) |