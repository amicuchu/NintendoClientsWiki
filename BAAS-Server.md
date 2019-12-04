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
| POST | `/1.0.0/login` |
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