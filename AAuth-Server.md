[[Server List]] > AAuth Server
---

This server is at: https://aauth-lp1.ndas.srv.nintendo.net

The aauth server provides application authorization tokens. These are required to access game-specific servers, such as [NEX](NEX-Overview-(Game-Servers)). This server takes form-encoded requests and responds with json-encoding. Also, this server uses the alternative base64 table (with '-' and '_' instead of '+' and '/')

## Methods
| Method | URL |
| --- | --- |
| POST | <code><a href="#post-v3challenge">/v3/challenge</a></code> |
| POST | <code><a href="#post-v3application_auth_token">/v3/application_auth_token</a></code> |

### POST /v3/challenge
| Param | Description |
| --- | --- |
| device_auth_token | Device token from [dauth server](DAuth-Server) |

### POST /v3/application_auth_token
The format of this request depends on the media type of the game.

| Param | Description |
| --- | --- |
| application_id | Title id |
| application_version | Title version |
| device_auth_token | Device token from [dauth server](DAuth-Server) |
| media_type | `GAMECARD` |
| gvt | ? |
| cert | Base64-encoded gamecard certificate (stored on game card itself) |

## Errors
On error, the server sends the following response:

| Field | Description |
| --- | --- |
| errors | List of errors |

Every error is encoded like this:

| Field | Description |
| --- | --- |
| code | Error code (string with 4 digits) |
| message | Error message |

### Known Errors
| Code | Message |
| --- | --- |
| 0118 | Invalid parameter in request. |