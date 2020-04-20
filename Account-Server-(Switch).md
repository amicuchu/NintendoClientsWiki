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
`/2.0.0/users/me` and `/api/1.0.0/users/<id>/qrcode_param`:

| Name | Description |
| --- | --- |
| invalid_token | ? |
| insufficient_scope | ? |
| under_maintenance | ? |

`/connect/1.0.0/api/token`:
| Name | Detail | Description |
| --- | --- | --- |
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
| unauthorized_client | | ? |
| unsupported_grant_type | | ? |
| server_error | | ? |
| under_maintenance | | ? |

| Name | Detail | Description |
| --- | --- | --- |
| unauthorized_client | | ? |
| access_denied | | ? |
| access_denied | id_token_hint_invalid | ? |
| access_denied | user_deleted | ? |
| invalid_scope | | ? |
| invalid_scope | scope_token_unknown | ? |
| invalid_scope | scope_token_prohibited | ? |
| server_error | | ? |
| login_required | | ? |
| login_required | user_not_logged_in | ? |
| login_required | user_different_from_id_token_hint | ? |
| consent_required | | ? |
| interaction_required | | ? |
| interaction_required | user_banned | ? |
| interaction_required | user_suspended | ? |
| interaction_required | user_terms_agreement_required | ? |
| under_maintenance | | ? |