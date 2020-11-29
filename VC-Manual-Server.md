## [Server List](Server-List.md) > VC Manuals

This server provides manuals for Wii games.

The manuals are at: `http://m1.nintendo.net/docvc/RVL/<region>/<gameid>/<gameid>_<language>.pdf`

`gameid` consists of 4 uppercase letters and digits. The cover of the game disk is one of the places where it can be found, usually prefixed by RVL-.

`region` should be one of `JPN`, `USA`, `EUR`, `CHN`, `KOR` or `TWN`.

`language` is always a single character:

| Code | Language |
| --- | --- |
| J | Japanese |
| E | English |
| F | French |
| G | German |
| I | Italian |
| S | Spanish |
| K | Korean |
| D | Dutch |
| P | Portuguese |
| R | Russian |
| T | Traditional |

If an invalid language code is specified the server returns the English manual.

Example url: http://m1.nintendo.net/docvc/RVL/EUR/RMGP/RMGP_E.pdf