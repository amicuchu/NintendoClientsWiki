# Table of Contents
1. [String](#string)
2. [Buffer](#buffer)
3. [Structure](#structure)

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

# Structure
NEX v3.5.0 introduced a versioning system to structures. Before v3.5.0 their contents were just normally stored into the stream. However, starting with v3.5.0, structured are stored like this:

| Type | Description |
| --- | --- |
| Uint8 | Version |
| Uint32 | Content length |
| | Content |
