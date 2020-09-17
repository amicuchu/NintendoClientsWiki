[[Server List]] > Eagle (dedicated servers)
---

Unlike most multiplayer games, Tetris 99 and Super Mario Bros. 35 use a dedicated server instead of [PIA](PIA-Overview), which seems to be called eagle. Match making is still done with [NEX](NEX-Overview-(Game-Servers)), but when the session is ready, the server sends a [notification event](Notification-Protocol) to the clients, which contains the url of the eagle server and a token.

* [Server URL](#server-url)
* [Token Format](#token-format)

### Server URL
The URL is written as follows: `<scheme>://<host>:<port>/<path>`.

The scheme must be either `kdp` (see https://github.com/skywind3000/kcp), `tcp`, `tcps`, `ws` or `wss`.

The port is optional and defaults to 443 if the connection is secured with TLS (`tcps` or `wss`) or 30000 if the connection is not secured with TLS. The path is only required on WebSocket connections (`ws` or `wss`). If TCP is used (`tcp` or `tcps`) packets are prefixed by a 16-bit little-endian integer that indicates the size of the packet.

The real server always uses the following URL: `wss://<server name>.g.<server env>.e.srv.nintendo.net:443/<game id>/ess-d7d-<server id>`.

| Game | Server Name | Game ID |
| --- | --- | --- |
| Tetris 99 | `d7d-arzn` | `EA3nJiq9BKyoxmBjJ2TkfzcRHwQe88FJ` |
| Super Mario Bros. 35 | `d7d-ayam-b` | `EGrCObHITxTtIa3O1A01uw2WHSEypGYb` |

Example: `wss://d7d-arzn.g.lp1.e.srv.nintendo.net:443/EA3nJiq9BKyoxmBjJ2TkfzcRHwQe88FJ/ess-d7d-btb4mnggg9q5k2kdqb8g`

### Token Format
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
