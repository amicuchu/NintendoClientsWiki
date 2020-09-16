[[Server List]] > Eagle (dedicated servers)
---

Unlike most multiplayer games, Tetris 99 and Super Mario Bros. 35 use a dedicated server instead of [PIA](PIA-Overview), which seems to be called eagle. Match making is still done with [NEX](NEX-Overview-(Game-Servers)), but when the session is ready, the server sends a [notification event](Notification-Protocol) to the clients, which contains the url of the eagle server and a token.

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

The url of the eagle server is `<protocol>://<server name>.g.<server env>.e.srv.nintendo.net:443/<game id>/ess-d7d-<server id>`.

| Game | Server Name | Game ID |
| --- | --- | --- |
| Tetris 99 | `d7d-arzn` | `EA3nJiq9BKyoxmBjJ2TkfzcRHwQe88FJ` |
| Super Mario Bros. 35 | `d7d-ayam-b` | `EGrCObHITxTtIa3O1A01uw2WHSEypGYb` |

The protocol must be either `kdp`, `tcp`, `tcps`, `ws` or `wss`. The real servers always use `wss`.

Example: `wss://d7d-arzn.g.lp1.e.srv.nintendo.net:443/EA3nJiq9BKyoxmBjJ2TkfzcRHwQe88FJ/ess-d7d-btb4mnggg9q5k2kdqb8g`