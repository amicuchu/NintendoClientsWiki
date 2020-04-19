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
| error_detail | Error details (optional) |

### Known Errors
| Name | Detail | Description |
| --- | --- | --- |
| invalid_token | ? | ? |
| insufficient_scope | ? | ? |
| under_maintenance | ? | ? |
| invalid_request | | The request does not satisfy the schema |
| invalid_client | | Client authentication failed |
| invalid_grant | | ? |
| invalid_grant | user_deleted | ? |
| invalid_grant | user_banned | ? |
| invalid_grant | user_suspended | ? |
| invalid_grant | user_withdrawn | ? |
| invalid_grant | user_terms_agreement_required | ? |
| invalid_scope | | ? |
| invalid_scope | scope_token_unknown | The requested scope is invalid |
| invalid_scope | scope_token_prohibited | ? |
| invalid_scope | scope_token_not_authorized | ? |