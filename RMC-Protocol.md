This is a simple remote method call protocol that lies on top of the [[PRUDP protocol]].

## Request Format
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Size, excluding this field |
| 0x4 | 1 | [Protocol id](NEX-Protocols), ORed with 0x80 |
| 0x5 | 4 | Call id, an incrementing number used to match a response to the right request |
| 0x9 | 4 | Method id |
| 0xD | ... | Method parameters |

## Response Format
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Size, excluding this field |
| 0x4 | 1 | [Protocol id](NEX-Protocols) |
| 0x5 | 1 | 0=Error 1=Success |

**On success:**

| Offset | Size | Description |
| --- | --- | --- |
| 0x6 | 4 | Call id |
| 0xA | 4 | Method id, ORed with 0x8000 |
| 0xE | ... | Response data |

**On error:**

| Offset | Size | Description |
| --- | --- | --- |
| 0x6 | 4 | Error code, see [errors.py](https://github.com/Kinnay/NintendoClients/blob/master/nintendo/nex/errors.py) |
| 0xA | 4 | Call id |
