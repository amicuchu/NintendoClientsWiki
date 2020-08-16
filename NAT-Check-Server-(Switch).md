This server is used to detect NAT properties of the router in order to perform NAT traversal.

This server is at:
* nncs1-lp1.n.n.srv.nintendo.net (primary server)
* nncs2-lp1.n.n.srv.nintendo.net (secondary server)

The protocol consists of simple UDP messages through port 10025 (primary port) or 10125 (secondary port). Messages are encoded in big endian byte order.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Message type |
| 0x4 | 4 | External port number. This is filled in by the server. |
| 0x8 | 4 | External IP address. This is filled in by the server. |
| 0xC | 4 | Unknown |

The Switch always starts the NAT check by sending [message type 1](#message-1) to the server. What happens next depends on the response of the server.

## Message 1
This message has several purposes:
1. The Switch uses it to find a working NAT check server. Usually, the primary server and port work fine. However, if the Switch does not receive a response after a given amount of time it tries the secondary port. If that doesn't work either it moves on to the secondary server.
2. The Switch measures the time until it receives a response. This is used as a timeout for subsequent messages.
3. The Switch compares the external ip and port in the response against its local ip and port. If they are the same, the Switch is connected directly to the internet and is not behind a NAT device. In other cases, the Switch moves on to [message type 2](#message-2).

## Message 2