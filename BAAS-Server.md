[[Server List]] > BAAS Server
---

Server: https://e0d67c509fb203858ebcb2fe3f88c2aa.baas.nintendo.com

This server takes form-encoded requests and responds with json-encoding.

## Headers
| Header | Description |
| --- | --- |
| X-Nintendo-PowerState | 'FA' (fully awake) or 'HA' (half awake) |

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
| assertion | device token obtained from dauth server |

Response on success:

| Field | Description |
| --- | --- |
| expiresIn | Expiration in seconds (10800) |
| accessToken | Authorization token for further request |
| tokenType | Authorization token type ("Bearer") |