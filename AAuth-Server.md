[[Server List]] > AAuth Server
---

Server: https://aauth-lp1.ndas.srv.nintendo.net

This server takes form-encoded requests and responds with json-encoding.

## Methods
| Method | URL |
| --- | --- |
| POST | `/v3/challenge` |
| POST | `/v3/application_auth_token` |

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