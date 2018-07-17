# Table of Contents
1. [String](#string)
2. [Buffer](#buffer)
3. [qBuffer](#qbuffer)
4. [List](#list)
5. [Map](#map)
6. [PID](#pid)
7. [DateTime](#date-time)
8. [StationURL](#station-url)
9. [Variant](#variant)
10. [Structure](#structure)
11. [Data](#any-data-holder)
12. [RVConnectionData](#rendez-vous-connection-data-structure)
13. [ResultRange](#result-range-structure)

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

# qBuffer
| Type | Description |
| --- | --- |
| Uint16 | Length |
| Bytes | Data |

# List
| Type | Description |
| --- | --- |
| Uint32 | Number of entries |
| | Entries |

# Map
A map is a [list](#list) of (key, value) pairs.

# PID
Every user and server is given a unique id called principal id.

| Platform | Type |
| --- | --- |
| 3DS / Wii U | Uint32 |
| Switch | Uint64 |

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

A station url contains the address and port of a server or client, along with a few parameters. The order of the fields is arbitrary. Here's an example station url: `prudps:/stream=10;sid=1;CID=1;type=2;address=34.210.222.104;port=60101;PID=2`

| Field | Description |
| --- | --- |
| &lt;scheme&gt; | udp, prudp or prudps |
| address | Address |
| port | Port |
| stream | Stream type |
| sid | Stream id |
| CID | Connection id |
| PID | Principal id |
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

The following fields were added on Nintendo Switch:

| Field | Description |
| --- | --- |
| Uri | Uri |
| R | Use relay server (0 or 1) |
| Rsa | Relay server address |
| Rsp | Relay server port |
| Ra | Relay address |
| Rp | Relay port |
| Tpt | Transport protocol type |
| Pl | Platform type |
| Ntrpa | NAT traversal requester private address |
| Ntrpp | NAT traversal requester private port |

# Variant
A variant consists of an uint8 indicating the type followed by its value.

| Type id | Type |
| --- | --- |
| 0 | None |
| 1 | Sint64 |
| 2 | Double |
| 3 | Bool |
| 4 | [String] |
| 5 | [DateTime] |
| 6 | Uint64 |

# Structure
NEX v3.5.0 introduced a versioning system to structures. Before v3.5.0 their contents were just normally stored into the stream. However, starting with v3.5.0, structures are stored like this:

| Type | Description |
| --- | --- |
| Uint8 | Version |
| Uint32 | Content length |
| | Content |

A structure may inherit another structure. The child is stored right after the parent, and gets its own version header.

# Any Data Holder
NEX has a class that can hold any object derived from nn::nex::Data. When these are transmitted as part of request or response data, some meta data is sent along with them, so the other side can properly identify and decode the object.

| Type | Description |
| --- | --- |
| [String] | Type name |
| Uint32 | Length of data, including the next length field |
| Uint32 | Length of data |
| | Object data |

# Rendez-Vous Connection Data ([Structure])
Nintendo does not use any special protocols.

| Type | Version | Name | Description |
| --- | --- | --- | --- |
| [StationURL](#station-url) | Any | m_urlRegularProtocols | Server address (regular protocols) |
| [List](#list)&lt;byte&gt; | Any | m_lstSpecialProtocols | Special protocols |
| [StationURL](#station-url) | Any | m_urlSpecialProtocols | Server address (special protocols) |
| [DateTime](#date-time) | V1 | m_currentUTCTime | Time |

Examples:

| Game | Secure server |
| --- | --- |
| Friends | `prudps:/stream=10;type=2;PID=2;port=60091;address=35.162.205.114;sid=1;CID=1` |
| DKC:TF | `prudps:/port=43221;CID=1;address=34.208.166.202;PID=2;stream=10;type=2;sid=1` |
| MK8 | `prudps:/sid=1;port=59201;address=52.10.188.163;PID=2;stream=10;type=2;CID=1` |

# Result Range ([Structure])
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | m_uiOffset | Offset |
| Uint32 | m_uiSize | Length |

[String]: #string
[Structure]: #structure
[DateTime]: #date-time