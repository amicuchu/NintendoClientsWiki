As an alternative to [PRUDP](PRUDP-Protocol), Nintendo provides an HTTP server that can be used to call [NEX methods](NEX-Protocols).

The server is at `https://hpp-<game server id>-<environment>.n.app.nintendo.net/hpp/`. The environment is one of L, C, S, D, I, T, J or U, followed by a single decimal digit.

The following headers are sent in requests:

| Header | Description |
| --- | --- |
| pid | User id |
| version | NEX version (e.g. `NEX_3_4_0`) |
| token | Always "normaltoken" |
| signature1 | Access key signature |
| signature2 | Password signature |

The signatures are a HMAC-MD5 over the request buffer. The key of signature1 is the access key of the game server, padded with zeroes until it is 8 bytes long. The key of signature2 is derived from the account password, using the [Kerberos key derivation](Kerberos-Authentication#key-derivation) algorithm.

Most game servers can not be accessed through the hpp server, but the following servers are known to work:

| Game Server ID | Game |
| --- | --- |
| 0008c500 | Tomodachi Collection: Shin Seikatsu |
| 10110e00 | Super Smash Bros. 4 (Wii U)|