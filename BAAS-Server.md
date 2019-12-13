[[Server List]] > BAAS Server
---

Server: https://e0d67c509fb203858ebcb2fe3f88c2aa.baas.nintendo.com

This server takes form-encoded requests and responds with json-encoding.

## Headers
| Header | Description |
| --- | --- |
| User-Agent | `libcurl (nnAccount; 789f928b-138e-4b2f-afeb-1acae821d897; SDK 9.3.0.0; Add-on 9.3.0.0)`
| X-Nintendo-PowerState | `FA` (fully awake) or `HA` (half awake) |

## Methods
| Method | URL |
| --- | --- |
| POST | <code><a href="#post-100applicationtoken">/1.0.0/application/token</a></code> |
| POST | <code><a href="#post-100login">/1.0.0/login</a></code> |
| POST | `/1.0.0/federation` |
| POST | `/1.0.0/users` |
| GET | `/1.0.0/users/<id>` |
| PATCH | `/1.0.0/users/<id>` |
| DELETE | `/1.0.0/users/<id>/device_accounts/<id>` |
| POST | `/1.0.0/users/<id>/link` |
| POST | `/1.0.0/users/<id>/unlink` |
| POST | `/1.0.0/image_upload` |
| PUT | `/1.0.0/push_channels/<id>/<id>` |

### POST /1.0.0/application/token
This request provides an authorization token that's required for all other requests.

| Param | Description |
| --- | --- |
| grantType | "public_client" |
| assertion | Device token obtained from [dauth server](DAuth-Server) |

Response on success:

| Field | Description |
| --- | --- |
| expiresIn | Expiration in seconds (10800) |
| accessToken | Authorization token for further requests |
| tokenType | Authorization token type ("Bearer") |

### POST /1.0.0/login
| Param | Description |
| --- | --- |
| id | User id |
| password | Password |
| appAuthNToken | [AAuth token](AAuth-Server) (optional) |
| skipOp2Verification | Unknown (optional) |

## Errors
On error, the server sends the following response:

| Field | Description |
| --- | --- |
| status | HTTP status code |
| errorCode | Error name |
| title | Error description |
| detail | Error description |
| instance | Path of the request that failed |
| type | `https://baas.nintendo.com/errors/1.0.0/<status>/<errorCode>` |

### Known Errors
| Status | Code | Title | Detail |
| --- | --- | --- | --- |
| 404 | resource_is_not_found | Specified resource is not found | Resource is not found |
| 405 | method_not_allowed | Method Not Allowed | Method Not Allowed |
| 400 | invalid_params | Invalid Params | invalid params |
| 400 | invalid_request | ? | ? |
| 400 | invalid_device_account | ? | ? |
| 400 | invalid_ndas_app_authn_token | ? | ? |
| 400 | invalid_idp | ? | ? |
| 400 | invalid_idp_account | ? | ? |
| 400 | linked_user_not_found | ? | ? |
| 400 | invalid_friend_code_format | ? | ? |
| 400 | user_link_not_exist | ? | ? |
| 400 | invalid_raw_content | ? | ? |
| 401 | invalid_token | ? | ? |
| 403 | insufficient_scope | ? | ? |
| 403 | forbidden | ? | ? |
| 403 | membership_required | ? | ? |
| 403 | unavailable_device_account | ? | ? |
| 403 | banned_user | ? | ? |
| 403 | banned_user_by_application | ? | ? |
| 404 | deleted_user | ? | ? |
| 406 | not_acceptable_language | ? | ? |
| 409 | resource_already_exists | ? | ? |
| 409 | user_link_already_exists | ? | ? |
| 412 | precondition_failed | ? | ? |
| 422 | friend_code_unregenerable_state | ? | ? |
| 500 | internal_server_error | ? | ? |
| 502 | could_not_confirm_membership | ? | ? |
| 503 | under_maintenance | ? | ? |