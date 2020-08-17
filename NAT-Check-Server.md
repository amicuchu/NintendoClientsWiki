This server is used to detect NAT properties of the router in order to perform NAT traversal.

This server is at:<br>
- `nncs1.app.nintendowifi.net` (Wii U, primary server)
- `nncs2.app.nintendowifi.net` (Wii U, secondary server)
- `nncs1-%.n.n.srv.nintendo.net` (Switch, primary server)
- `nncs2-%.n.n.srv.nintendo.net` (Switch, secondary server)

The protocol consists of simple UDP messages through port 10025 (primary port) or 10125 (secondary port). Messages are encoded in big endian byte order.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | [Message type](#message-types) |
| 0x4 | 4 | External port number. This is filled in by the server. |
| 0x8 | 4 | External IP address. This is filled in by the server. |
| 0xC | 4 | NEX fills in its external IP address (after it has received a response to [message type 1](#message-types)). The server fills in its own local IP address. |

## Message Types
| Type | Description |
| --- | --- |
| 1 | The server replies from its regular IP address and port. NEX uses this to check if the NAT check server is reachable at all, to measure the time that it takes to receive a response, and to figure out its own external IP address and port. |
| 2 | The server replies from a different IP address and port. NEX uses this to determine the NAT filtering mode. |
| 3 | The server replies from its regular IP address but from a different port. NEX uses this to determine the NAT filtering mode. |
| 4 | The server replies from its regular IP address and port. NEX uses this to determine the NAT mapping mode. |
| 5 | The server replies from its regular IP address and port. NEX uses this to determine the NAT mapping mode. |

| Type | Description |
| --- | --- |
| 101 | The server replies from its regular IP address and port. |
| 102 | The server replies from its regular IP address but from a different port. |
| 103 | The server replies from its regular IP address and port. |
