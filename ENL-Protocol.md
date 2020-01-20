ENL is Nintendo's private peer-to-peer framework that uses [PIA](PIA-Overview) and [NEX](NEX-Overview-(Game-Servers)) internally. It is used by many first-party games, such as Mario Kart 8, Splatoon 2 and Super Mario Maker 2.

Check out the pages about [PIA](PIA-Overview) for details on how a peer-to-peer session is set up. Once the session is ready, ENL sends all packets through the [unreliable protocol](Unreliable-Protocol).

To transmit game-data, games can register content transporters to ENL. ENL also implements a few content transporters on its own.

A message consists of one or more records, terminated by a record with type 0xFF.

## Record Header
| Type | Description |
| --- | --- |
| Uint8 | Record type |
| Uint16 | Record size |
| Bytes | Record data |

| Record Type | Description |
| --- | --- |
| 0xFD | System request info |
| 0xFE | System information |
| 0xFF | End record |

Other record types may be implemented by game-specific content transporters.