[[Server List]] > Account Server (Switch)
---

This server takes form-encoded requests and responds with json-encoding.

## Methods
**accounts.nintendo.com:**

| Method | URL |
| --- | --- |
| POST | `/connect/1.0.0/api/token` |
| POST | `/connect/1.0.0/api/authorize` |
| GET | `/api/1.0.0/users/<id>/qrcode_param` |

**api.accounts.nintendo.com:**

| Method | URL |
| --- | --- |
| GET | `/2.0.0/users/me` |

## Errors
On error, the server sends the following response:

| Field | Description |
| --- | --- |
| error | Error name |
| error_description | Error description |
| error_detail | Optional, only sometimes present |

### Known Errors
| Name | Detail | Description |
| --- | --- | --- |
| invalid_request | - | The request does not satisfy the schema |
| invalid_scope | scope_token_unknown | The requested scope is invalid |
| invalid_client | - | Client authentication failed |