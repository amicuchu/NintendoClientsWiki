[[Server List]] > Eagle (relay servers)
---

Unlike most multiplayer games, Tetris 99 and Super Mario Bros. 35 use a relay server instead of [PIA](PIA-Overview), which seems to be called eagle. Match making is still done with [NEX](NEX-Overview-(Game-Servers)), but when the session is ready, the server sends a [notification event](Notification-Protocol) to the clients, which contains the url of the eagle server and a token.

* [Server URL](#server-url)
* [Token Format](#token-format)
* [Packet Format](#packet-format)

## Server URL
The URL is written as follows: `<scheme>://<host>:<port>/<path>`.

The scheme must be either `kdp` (see https://github.com/skywind3000/kcp), `tcp`, `tcps`, `ws` or `wss`.

The port is optional and defaults to 443 if the connection is secured with TLS (`tcps` or `wss`) or 30000 if the connection is not secured with TLS. The path is only required on WebSocket connections (`ws` or `wss`). If TCP is used (`tcp` or `tcps`) packets are prefixed by a 16-bit little-endian integer that indicates the size of the packet.

The real server always uses the following URL: `wss://<server name>.g.<server env>.e.srv.nintendo.net:443/<game id>/ess-d7d-<server id>`.

| Game | Server Name | Game ID |
| --- | --- | --- |
| Tetris 99 | `d7d-arzn` | `EA3nJiq9BKyoxmBjJ2TkfzcRHwQe88FJ` |
| Super Mario Bros. 35 | `d7d-ayam-b` | `EGrCObHITxTtIa3O1A01uw2WHSEypGYb` |

Example: `wss://d7d-arzn.g.lp1.e.srv.nintendo.net:443/EA3nJiq9BKyoxmBjJ2TkfzcRHwQe88FJ/ess-d7d-btb4mnggg9q5k2kdqb8g`

## Token Format
The token is a base64-encoded JSON object that contains the following fields:

| Field | Description |
| --- | --- |
| payload | Payload. See below. |
| signature | Base64-encoded signature (32 bytes) |
| version | Always 1 |

The payload has the following fields:

| Field | Description |
| --- | --- |
| expires_at | Timestamp in seconds (string) |
| server_env | Server environment (e.g. `lp1`) |
| server_id | A string of 20 lowercase alphanumeric characters. The server of SMB35 also adds the suffix "-blue". |
| user_id | Your pid (hex string) |

## Packet Format
Packets are encoded as a stream of bits. Each packet starts with the following header:

| Bits | Description |
| --- | --- |
| 2 | Relay type |
| 8 | Payload id |
| 9 | Source node id |

The remainder of the packet depends on the relay type and payload id.

| Type | Description |
| --- | --- |
| 0 | No relay. |
| 1 | This packet is relayed to a single node. The header is followed by 9 bits that hold the destination node id. |
| 2 | This packet is relayed to multiple nodes. The header is followed by 128 bits that hold the destination nodes (one bit per node). |

The payload comes after header and relay destination, but the bit stream is first aligned to 8 bits before the payload starts.

| Payload ID | Description |
| --- | --- |
| 0 | [Connection accepted](#connection-accepted) |
| 1 | [Login request](#login-request) |
| 2 | [Login result](#login-result) |
| 3 | Client ready |
| 4 | Unknown |
| 5 | Unknown |
| 6 | Unknown |
| 7 | Unknown |
| 8 | Unknown |
| 9 | Unknown |

### Connection Accepted
| Bits | Description |
| --- | --- |
| 16 | Node id |
| 64 | Server time (in milliseconds) |

### Login Request
| Bits | Description |
| --- | --- |
| 7 | Login phase (0 or 1) |
| 1 | Unknown |

Login phase 0:
| Bits | Description |
| --- | --- |
| 8 | Unknown |
| 32 | Unknown |
| 64 | Unknown |
| 32 | Unknown |
| 8 | Version string size (max 64 bits) |
| | Version string |

Login phase 1:
| Bits | Description |
| --- | --- |
| 8 | Token string size |
| | Token string |

### Login Result
| Bits | Description |
| --- | --- |
| 32 | Unknown |
| 8 | Unknown |
| 16 | Payload size |
| | Payload |