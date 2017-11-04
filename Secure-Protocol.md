## [[NEX Protocols]] > Secure Connection (0x0B)

| Method ID | Method Name |
| --- | --- |
| 1 | [Register](#1-register) |
| 2 | [RequestConnectionData](#2-requestconnectiondata) |
| 3 | [RequestUrls](#3-requesturls) |
| 4 | [RegisterEx](#4-registerex) |
| 5 | [TestConnectivity](#5-testconnectivity) |
| 6 | [UpdateUrls](#6-updateurls) |
| 7 | [ReplaceUrl](#7-replaceurl) |
| 8 | [SendReport](#8-sendreport) |

# (1) Register
The secure server keeps a list of client urls that can be registered (added) and replaced by the client.

## Request
| Type | Description |
| --- | --- |
| [List]&lt;[String]&gt; | Local client urls |

## Response
| Type | Description |
| --- | --- |
| Uint32 | Result code |
| Uint32 | Connection id |
| [StationURL] | Public client url, as perceived by the server |

The client should place the connection id into the RVCID field of its client station urls.

# (2) RequestConnectionData

# (3) RequestUrls

# (4) RegisterEx
## Request
| Type | Description |
| --- | --- |
| [List]&lt;[String]&gt; | Local client urls |
| [Data]&lt;[NintendoLoginData](#nintendo-login-data)&gt; | Login data |

### Nintendo Login Data
| Type | Description |
| --- | --- |
| [String] | Token (received from the account server) |

## Response
Same as response for the [Register](#1-register) method.

# (5) TestConnectivity

# (6) UpdateUrls

# (7) ReplaceUrl

# (8) SendReport

[List]: NEX-Common-Types#list
[String]: NEX-Common-Types#string
[StationURL]: NEX-Common-Types#station-url
[Data]: NEX-Common-Types#any-data-holder