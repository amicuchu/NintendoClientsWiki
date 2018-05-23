PRUDP is a transport layer protocol on top of UDP whose aim is to reliably send UDP packets. There are two version of this protocol ([V0](#v0-format) and [V1](#v1-format)), but these are pretty similar. The only difference lies in the way the packets are encoded. All values are encoded in little endian byte order.

On the Nintendo Switch, NEX can be configured to use TCP or WebSockets instead of UDP. In that case, the '[Lite](#lite-format)'-encoding is used.

### Basic operation
When a client connects to a server, it sends a SYN packet. As soon as this packet is acknowledged by the server, it sends a CONNECT packet. When this packet has been acknowledged too, a connection has been made and the client and server can start sending DATA packets. If the client wants to close the connection, it sends a DISCONNECT packet. This packet is acknowledged three times by the server, presumably to ensure the client receives the ACK.

The following techniques are used to achieve reliability:
* A packet that has FLAG_NEED_ACK set must be acknowledged by the receiver. If the sender doesn't receive an acknowledgement after a certain amount of time it will resend the packet.
* A [sequence id](#sequence-id) is sent along with a packet, so the receiver can reorder packets if necessary.
* To keep the connection alive, both client and server send PING packets to each other after a certain amount of time has passed.

### Secure server connection
While the payload should be empty when connecting to the authentication server, the secure server requires the following data to be in the payload of the CONNECT packet:

#### Connection request
| Type | Description |
| --- | --- |
| [Buffer] | Kerberos ticket data |
| [Buffer] | [Kerberos-encrypted](Kerberos-Authentication) request data |

Request data:

| Type | Description |
| --- | --- |
| [PID] | User pid |
| Uint32 | CID of secure server station url |
| Uint32 | Response check value |

#### Connection response
The CONNECT acknowledgement packet contains a [Buffer] with the following data:

| Type | Description |
| --- | --- |
| Uint32 | Response check value + 1 |

### Encryption
All payloads are encrypted using RC4, with separate streams for client-to-server packets and server-to-client packets. The connection to the authentication server is encrypted using a default key that's always the same: `CD&ML`. The connection to the secure server is encrypted using the secure key from the [Kerberos ticket](Kerberos-Authentication#kerberos-ticket).

### Virtual ports
When multiple PRUDP connections are made to the same address, NEX doesn't create a new socket for each connection. Instead, it uses a single socket to create multiple PRUDP connections. To distinguish between connections, each packet contains a source and destination port.

**V0 and V1**: The four most significant bits contain the stream type. The four least significant bits contain the port number. The client port is the highest unused port number &le; 0xF.

**Lite**: The port number now uses 8 bits instead of 4. The client port is the highest unused port number &le; 0x1F. The stream types are stored in a separate byte.

**Server port (3DS/Wii U)**: The authentication and secure server may not reside at the same address. The server port is always 1.

**Server port (Switch)**: A single websocket server handles both authentication and secure connections. The authentication server has server port 1, the secure server has server port 2.

The stream type is always RVSecure (0xA) in Nintendo games.

| Stream type | Name | Stream type | Name |
| --- | --- | --- | --- |
| 1 | DO | 7 | NATEcho |
| 2 | RV | 8 | Routing |
| 3 | OldRVSec | 9 | Game |
| 4 | SBMGMT | 10 | RVSecure |
| 5 | NAT | 11 | Relay |
| 6 | SessionDiscovery | | |

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

### Aggregate acknowledgement
To acknowledge multiple packets at once, send a DATA packet with FLAG_MULTI_ACK. All packets up to the specified packet id will be acknowledged. The payload should contain the following data:

#### Old version
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 2 | Packet id |

#### New version
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Unknown (always 0?) |
| 0x1 | 1 | Unknown (always 0?) |
| 0x2 | 2 | Packet id |

Since the version can only be specified in the [V1](#v1-format) header, [V0](#v0-format) probably only supports the old version. The [Lite](#lite-format) format always uses the new version. 

### Session id
This is a random value generated at the start of each session. The server's session id is not necessarily the same as the client's session id.

### Sequence id
This is an incrementing value used to ensure that packets arrive in correct order. The sequence id of client-to-server packets is separate from the sequence id of server-to-client packets.

### Fragment id
Big data packets are split into smaller ones. The last fragment always has fragment id 0. Other fragments have an incrementing fragment id starting at 1.

For example, if a packet is split into four fragments, they will have the following fragment ids:

| Fragment | Fragment id |
| --- | --- |
| First | 1 |
| Second | 2 |
| Third | 3 |
| Fourth | 0 |

### Connection signature
The server sends its connection signature in its response to the client's SYN packet. The client sends its connection signature in the CONNECT packet. Other SYN/CONNECT packets have this field set to 0.

If present, the connection signature is a HMAC based on the perceived ip and port of the other end point. Neither server nor client can verify this signature.

### Lite signature
Unlike the connection signature, this signature is actually verified by the server. It's the HMAC of the following data, with the key being the MD5 hash of the access key.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 16 | MD5 of access key |
| 0x10 | 16 | Connection signature received from server |

### Optional data
Starting with PRUDP V1, packet-specific data is encoded like this:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Option id |
| 0x1 | 1 | Value size |
| 0x2 | | Value |

| Option id | Size | Description |
| --- | --- | --- |
| 0 | 4 | Supported functions (unknown purpose) |
| 1 | 16 | [Connection signature](#connection-signature) |
| 2 | 1 | [Fragment id](#fragment-id) |
| 3 | 2 | Unknown (random integer) |
| 4 | 1 | Unknown (always 0) |
| 0x80 | 16 | [Lite signature](#lite-signature) |

## V0 Format
This format is only used by the friends server, and some 3DS games.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | [Source](#virtual-ports) |
| 0x1 | 1 | [Destination](#virtual-ports) |
| 0x2 | 2 | [Type and flags](#type-and-flags) |
| 0x4 | 1 | [Session id](#session-id) |
| 0x5 | 4 | [Packet signature](#packet-signature) |
| 0x9 | 2 | [Sequence id](#sequence-id) |
| 0xB | | Packet-specific data |
| | | Payload |
| | 1 | Checksum |

Packet-specific data:

| Only present if | Size | Description |
| --- | --- | --- |
| Type is SYN or CONNECT | 4 | [Connection signature](#connection-signature) |
| Type is DATA | 1 | [Fragment id](#fragment-id) |
| Flags & FLAG_HAS_SIZE | 2 | Payload size |

### Packet signature
**Friends server:**
* In DATA packets with an empty payload the packet signature is always set to 0x12345678.
* In all other DATA packets the signature is the first 4 bytes of the HMAC of the encrypted payload, with the key being the MD5 hash of the access key.
* In all other packets the signature is the connection signature that has been received while the connection was made.

**Games:**

In DATA and DISCONNECT packets the packet signature is the first 4 bytes of the HMAC of the following data, with the key being the MD5 hash of the access key:

| Size | Description |
| --- | --- |
| 0 or 16 | Secure key (or nothing in an authentication connection) |
| 2 | [Sequence id](#sequence-id) |
| 1 | [Fragment id](#fragment-id) |
| | Encrypted payload |

In all other packets the signature is the connection signature that has been received while the connection was made.

### Checksum
The checksum is calculated over the whole packet (both header and encrypted payload), and uses the following algorithm (the example code is written in python):
```python
def calc_checksum(checksum, data):
	#Little endian!
	words = struct.unpack_from("<%iI" %(len(data) // 4), data)
	temp = sum(words) & 0xFFFFFFFF #32-bit
	
	#Add the sum of the remaining bytes to the checksum
	checksum += sum(data[len(data) & ~3:])
	
	#And the sum of the bytes of the temporary checksum
	checksum += sum(struct.pack("I", temp))
	
	return checksum & 0xFF #8-bit checksum
	
checksum = calc_checksum(sum(ACCESS_KEY), packet_data)
```

## V1 Format
This format is used by all Wii U games and apps except for friends services, and possibly some 3DS games.

| Size | Description |
| --- | --- |
| 2 | Magic number: 0xEA 0xD0 |
| 12 | Packet header |
| 16 | [Packet signature](#packet-signature-1) |
| | Packet-specific data |
| | Payload |

### Packet header
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | PRUDP version (always 1) |
| 0x1 | 1 | Length of packet-specific data |
| 0x2 | 2 | Payload size |
| 0x4 | 1 | [Source](#virtual-ports) |
| 0x5 | 1 | [Destination](#virtual-ports) |
| 0x6 | 2 | [Type and flags](#type-and-flags) |
| 0x8 | 1 | [Session id](#session-id) |
| 0x9 | 1 | [Multi-ack](#aggregate-acknowledgement) version |
| 0xA | 2 | [Sequence id](#sequence-id) |

### Packet signature
The packet signature is the HMAC of the following data, with the key being the MD5 hash of the access key:

| Size | Description |
| --- | --- |
| 8 | Bytes 0x4 - 0xC of the packet header |
| 0, 16 or 32 | The secure key (not present in a connection to the authentication server) |
| 4 | Sum of all access key bytes (little endian) |
| 16 | Connection signature, or 16 zero-bytes if it has not yet been received |
| | Packet-specific data |
| | Payload |

### Packet-specific data
See [optional data](#optional-data).

| Option id | Only present if |
| --- | --- |
| 0 | Type is SYN or CONNECT |
| 1 | Type is SYN or CONNECT |
| 2 | Type is DATA |
| 3 | Type is CONNECT |
| 4 | Type is SYN or CONNECT |

## Lite Format
This format is used by Nintendo Switch games.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Magic number: 0x80 |
| 0x1 | 1 | Length of packet-specific data |
| 0x2 | 2 | Payload size |
| 0x4 | 1 | 0xXY (X = source stream type, Y = destination stream type) |
| 0x5 | 1 | [Source port](#virtual-ports) |
| 0x6 | 1 | [Destination port](#virtual-ports) |
| 0x7 | 1 | [Fragment id](#fragment-id) |
| 0x8 | 2 | [Type and flags](#type-and-flags) |
| 0xA | 2 | [Sequence id](#sequence-id) |
| 0xC | | Packet-specific data |
| | Payload |

Packet-specific data (see [optional data](#optional-data)):

| Option id | Only present if |
| --- | --- |
| 0 | Type is SYN or CONNECT |
| 1 | Type is SYN and Flags & FLAG_ACK |
| 0x80 | Type is CONNECT and not Flags & FLAG_ACK |

[Buffer]: NEX-Common-Types#buffer
[PID]: NEX-Common-Types#pid