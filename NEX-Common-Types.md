# Table of Contents
1. [String](#string)
2. [Buffer](#buffer)
3. [List](#list)
4. [DateTime](#date-time)
5. [StationURL](#station-url)
6. [Structure](#structure)
7. [Data](#any-data-holder)

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

# Any Data Holder
NEX has a class that can hold any object derived from nn::nex::Data. When these are transmitted as part of request or response data, some meta data is sent along with them, so the other side can properly identify and decode the object.

| Type | Description |
| --- | --- |
| [String] | Type name |
| Uint32 | Length of data, including the next length field |
| Uint32 | Length of data |
| | Object data |

[String]: #string

# Rendez-Vous Connection Data ([Structure](#structure))
Nintendo does not use any special protocols.

| Type | Version | Description |
| --- | --- | --- |
| [StationURL](#station-url) | Any | Server address (regular protocols) |
| [List](#list)&lt;byte&gt; | Any | Special protocols |
| [StationURL](#station-url) | Any | Server address (special protocols) |
| [DateTime](#date-time) | V1 | Server time |

Examples:

| Game | Secure server |
| --- | --- |
| Friends | `prudps:/stream=10;type=2;PID=2;port=60091;address=35.162.205.114;sid=1;CID=1` |
| DKC:TF | `prudps:/port=43221;CID=1;address=34.208.166.202;PID=2;stream=10;type=2;sid=1` |
| MK8 | `prudps:/sid=1;port=59201;address=52.10.188.163;PID=2;stream=10;type=2;CID=1` |
