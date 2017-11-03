# Table of Contents
1. [String](#string)
2. [Buffer](#buffer)
3. [List](#list)
4. [DateTime](#date-time)
5. [StationURL](#station-url)
6. [Structure](#structure)

# String
| Type | Description |
| --- | --- |
| Uint16 | Length (including null terminator) |
| Chars | Null terminated UTF-8 string |

# Buffer
| Type | Description |
| --- | --- |
| Uint32 | Length |
| Bytes | Data |

# List
| Type | Description |
| --- | --- |
| Uint32 | Number of entries |
| | Entries |

# Date Time
| Type | Description |
| --- | --- |
| Uint64 | Value |

This is not a normal time stamp. Instead, it consists of a bunch of bit fields:

| Bits | Description |
| --- | --- |
| 0 - 38 | Year |
| 38 - 42 | Month |
| 42 - 47 | Day |
| 47 - 52 | Hour |
| 52 - 58 | Minute |
| 58 - 64 | Second |

Note: 0 refers to the most significant bit.

# Station URL
| Type | Description |
| --- | --- |
| [String] | Station URL |

A station url contains the address and port of a server or client, along with a few parameters. The order of the fields is arbitrary. Here's an example of a station url: `prudps:/stream=10;sid=1;CID=1;type=2;address=34.210.222.104;port=60101;PID=2`

| Field | Description |
| --- | --- |
| &lt;protocol&gt; | udp, prudp or prudps |
| stream | Stream type |
| sid | Stream id |
| CID | Connection id |
| type | Type |
| RVCID | Rendez-vous connection id |
| natm | NAT mapping |
| natf | NAT filtering |
| upnp | UPnP support (0 or 1) |
| pmp | PMP support (0 or 1) |
| probeinit | Probe request initiation |
| PRID | Probe request id |
| fastproberesponse | Fast probe response |
| NodeID | Node id

# Structure
NEX v3.5.0 introduced a versioning system to structures. Before v3.5.0 their contents were just normally stored into the stream. However, starting with v3.5.0, structures are stored like this:

| Type | Description |
| --- | --- |
| Uint8 | Version |
| Uint32 | Content length |
| | Content |

[String]: #string
