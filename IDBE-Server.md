## [[Server List]] > IDBE Server

This server provides icon data for Wii U and 3DS titles.

| Platform | Server |
| --- | --- |
| 3DS | https://idbe-ctr.cdn.nintendo.net |
| Wii U | https://idbe-wup.cdn.nintendo.net |

An icon file can be retrieved by sending a GET request to one of the following URLs:

| URL | Description |
| --- | --- |
| `/icondata/<id>/<titleid>.idbe` | Provides the latest icon data for a title |
| `/icondata/<id>/<titleid>-<version>.idbe` | Provides the icon data for a specific version of a title |

The title id must be specified as 16 uppercase hex digits. The first id should be `(titleid >> 8) & 0xFF`. For example, if the title id is `0005000010137D00` then the first id should be `7D`. The server seems to ignore this value though.

## File Format
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Always 0 |
| 0x1 | 1 | Key type |
| 0x2 | | Encrypted [icon data](#icon-data-format) |

The icon data is encrypted with AES-CBC. The IV is always `a46987ae47d82bb4fa8abc0450285fa4`.

| Type | Key |
| --- | --- |
| 0 | `4ab9a40e146975a84bb1b4f3ecefc47b` |
| 1 | `90a0bb1e0e864ae87d13a6a03d28c9b8` |
| 2 | `ffbb57c14e98ec6975b384fcf40786b5` |
| 3 | `80923799b41f36a6a75fb8b48c95f66f` |

## Icon Data Format
Wii U files are encoded in big-endian byte order, 3DS files in little-endian byte order.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 32 | SHA256 checksum of the remaining data |
| 0x20 | 8 | Title id |
| 0x28 | 4 | Title version |
| 0x2C | 4 | Unknown |
| 0x30 | 4 | Unknown |
| 0x34 | 16 | Unknown |
| 0x44 | 4 | Unknown |
| 0x48 | 8 | Unknown |
| 0x50 | 0x200 x 16 | [Title strings](#title-strings) in different [languages](#languages) |

**Wii U:**
| Offset | Size | Description |
| --- | --- | --- |
| 0x2050 | 0x1002C | TGA file |
| 0x1207C | 4 | Unknown |

**3DS:**
| Offset | Size | Description |
| --- | --- | --- |
| 0x2050 | 0x1680 | Unknown |

### Title Strings
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 128 | Short name (utf-16) |
| 0x80 | 256 | Long name (utf-16) |
| 0x180 | 128 | Publisher name (utf-16) |

### Languages
The header has room for 16 languages but only 12 are actually used. The remaining languages have empty strings.

| Index | Language |
| --- | --- |
| 0 | Japanese |
| 1 | English |
| 2 | French |
| 3 | German |
| 4 | Italian |
| 5 | Spanish |
| 6 | Chinese (simple) |
| 7 | Korean |
| 8 | Dutch |
| 9 | Portuguese |
| 10 | Russian |
| 11 | Chinese (traditional) |

<!-- | 0x20 | 0x36B0 or 0x12060 | Icon data | -->