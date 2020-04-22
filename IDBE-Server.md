## [[Server List]] > IDBE Server

This server provides icon databases for Wii U and 3DS titles.

| Platform | Server |
| --- | --- |
| 3DS | https://idbe-ctr.cdn.nintendo.net |
| Wii U | https://idbe-wup.cdn.nintendo.net |

An icon database can be retrieved by sending a GET request to one of the following URLs:

| URL | Description |
| --- | --- |
| `/icondata/<id>/<titleid>.idbe` | Provides the latest icon database for a title |
| `/icondata/<id>/<titleid>-<version>.idbe` | Provides the icon database for a specific version of a title |

The first id should be `(titleid >> 8) & 0xFF`. For example, if the title id is `0005000010137D00` then the first id should be `7D`. The server seems to ignore this value though.