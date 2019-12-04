[[Server List]] > AAuth Server
---

This server is at: https://aauth-lp1.ndas.srv.nintendo.net

The aauth server provides application authorization tokens. These are required to access game-specific servers, such as [NEX](NEX-Overview-(Game-Servers)).

This server takes form-encoded requests and responds with json-encoding. Also, this server uses the alternative base64 table (with '-' and '_' instead of '+' and '/')

## Headers
| Header | Description |
| --- | --- |
| User-Agent | `libcurl (nnAccount; 789f928b-138e-4b2f-afeb-1acae821d897; SDK 9.3.0.0; Add-on 9.3.0.0)` |

## Methods
| Method | URL |
| --- | --- |
| POST | <code><a href="#post-v3challenge">/v3/challenge</a></code> |
| POST | <code><a href="#post-v3application_auth_token">/v3/application_auth_token</a></code> |

### POST /v3/challenge
This request is only required if the media type is `GAMECARD`.

| Param | Description |
| --- | --- |
| device_auth_token | Device token from [dauth server](DAuth-Server) |

### POST /v3/application_auth_token
The following parameters are always present:

| Param | Description |
| --- | --- |
| application_id | Title id |
| application_version | Title version |
| device_auth_token | Device token from [dauth server](DAuth-Server) |
| media_type | `GAMECARD`, `DIGITAL`, `SYSTEM` or `NO_CERT` |

The following parameters depend on the media type of the game:

#### GAMECARD
| Param | Description |
| --- | --- |
| gvt | ? |
| cert | Base64-encoded gamecard certificate (stored on game card itself) |

#### DIGITAL
| Param | Description |
| --- | --- |
| cert | ? |
| cert_key | ? |

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