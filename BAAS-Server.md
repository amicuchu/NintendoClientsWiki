[[Server List]] > BAAS Server
---

Server: https://e0d67c509fb203858ebcb2fe3f88c2aa.baas.nintendo.com

This server takes form-encoded requests and responds with json-encoding.

## Headers
| Header | Description |
| --- | --- |
| User-Agent | [User agent](#user-agents) |
| X-Nintendo-PowerState | `FA` (fully awake) or `HA` (half awake). This header is only present in the <code><a href="post-100applicationtoken">/1.0.0/application/token</a></code> and <code><a href="#post-100login">/1.0.0/login</a></code> requests. |

#### User Agents
| System Version | User agent |
| --- | --- |
| 9.0.0 - 9.2.0 | `libcurl (nnAccount; 789f928b-138e-4b2f-afeb-1acae821d897; SDK 9.3.0.0; Add-on 9.3.0.0)` |
| 10.0.0 - 10.0.1 | `libcurl (nnAccount; 789f928b-138e-4b2f-afeb-1acae821d897; SDK 10.4.0.0; Add-on 10.4.0.0)` |

## Methods
| Method | URL |
| --- | --- |
| POST | <code><a href="#post-100applicationtoken">/1.0.0/application/token</a></code> |
| POST | <code><a href="#post-100login">/1.0.0/login</a></code> |
| POST | `/1.0.0/federation` |
| POST | <code><a href="#post-100users">/1.0.0/users</a></code> |
| GET | `/1.0.0/users` |
| GET | `/1.0.0/users/<id>` |
| PATCH | `/1.0.0/users/<id>` |
| PATCH | `/1.0.0/users/<id>/device_accounts/<id>` |
| DELETE | `/1.0.0/users/<id>/device_accounts/<id>` |
| POST | `/1.0.0/users/<id>/link` |
| POST | `/1.0.0/users/<id>/unlink` |
| GET | `/1.0.0/users/<id>/blocks` |
| POST | `/1.0.0/users/<id>/blocks` |
| DELETE | `/1.0.0/users/<id>/blocks/<id>` |
| POST | `/1.0.0/users/<id>/generate_code` |
| POST | `/1.0.0/image_upload` |
| PUT | `/1.0.0/push_channels/<id>/<id>` |
| GET | `/2.0.0/users/<id>friends` |
| PATCH | `/2.0.0/users/<id>/friends/<id>` |
| DELETE | `/2.0.0/users/<id>/friends/<id>` |
| GET | `/2.0.0/users/<id>/friend_requests/inbox` |
| GET | `/2.0.0/users/<id>/friend_requests/outbox` |
| POST | `/2.0.0/friend_requests` |
| PATCH | `/2.0.0/friend_requests/<id>` |
| GET | `/2.0.0/users/<id>/relationships/<id>` |
| GET | <code><a href="get-#100certificates">/1.0.0/certificates</a></code> |

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
This request can be used to log in on a device account that was registered with <code><a href="#post-100users">/1.0.0/users</a></code>. If an application token is provided, the server checks if the device account is linked against a Nintendo account, and if the account has a Nintendo Switch Online membership.

| Param | Description |
| --- | --- |
| id | Device account id |
| password | Device account password |
| appAuthNToken | [AAuth token](AAuth-Server) (optional) |
| skipOp2Verification | Unknown (optional) |

Response on success:

| Param | Description |
| --- | --- |
| expiresIn | Expiration in seconds (10800) |
| user | [User information](#user-information) |
| idToken | ID token (for game servers) |
| accessToken | Authorization token for further requests |
| tokenType | Authorization token type ("Bearer") |

### POST /1.0.0/users
This request registers a new user on the server. This request does not take any parameters. On success, the response contains the new [user information](#user-information) and HTTP status code 201.

### User information
| Field | Description |
| --- | --- |
| id | User id (16 hex digits) |
| etag | ETag |
| nickname | Nickname |
| country | Country |
| birthday | YYYY-MM-DD |
| thumbnailUrl | Thumbnail URL |
| deviceAccounts | List of [device accounts](#device-account) |
| links | [Linked accounts](#linked-accounts) |
| permissions | [Privacy settings](#privacy-settings) |
| extras | [Extras](#user-extras) |
| presence | [Online status](#online-status) |
| deleted | Bool |
| blocksUpdatedAt | Timestamp |
| friendsUpdatedAt | Timestamp |
| createdAt | Timestamp |
| updatedAt | Timestamp |

#### Device account
| Field | Description |
| --- | --- |
| id | Device account id (16 hex digits) |
| password | Device account password (30 random bytes, base64-encoded) |

#### Linked accounts
| Field | Description |
| --- | --- |
| nintendoNetwork | [Nintendo network link](#linked-account) |
| twitter | [Twitter account link](#linked-account) |
| facebook | [Facebook account link](#linked-account) |
| google | [Google account link](#linked-account) |
| friendCode | [Friend code](#friend-code-link) |

#### Linked account
| Field | Description |
| --- | --- |
| id | Account id |
| createdAt | Timestamp |
| updatedAt | Timestamp |

#### Friend code link
| Field | Description |
| --- | --- |
| id | Friend code |
| createdAt | Timestamp |
| updatedAt | Timestamp |
| regenerableAt | Timestamp |
| regenerable | Bool |

#### Privacy settings
| Field | Description |
| --- | --- |
| personalAnalytics | Bool |
| personalNotification | Bool |
| friendRequestReception | Bool |
| friends | `EVERYONE` |
| presence | `FRIENDS`, `FAVORITE_FRIENDS` or `SELF` |
| presenceUpdatedAt | Timestamp |
| personalAnalyticsUpdatedAt | Timestamp |
| personalNotificationUpdatedAt | Timestamp |

#### Online status
| Field | Description |
| --- | --- |
| state | `OFFLINE`, `INACTIVE`, `ONLINE` or `PLAYING` |
| extras | [Extras](#presence-extras) |
| updatedAt | Timestamp |
| logoutAt | Timestamp |

#### Extras
| Field | Description |
| --- | --- |
| self | Extras visible by no one |
| favoriteFriends | Extras visible by best friends |
| friends | Extras visible by all friends |
| foaf | Extras visible by friends of a friend |
| everyone | Extras visible by everyone |

#### User extras
The following fields are stored in each of the [extras](#extras).

| Field | Description |
| --- | --- |
| playLog | JSON-encoded string containing a list of [play log entries](#play-log-entry) |
| nxAccount | String that identifies the account (only present in 'self'-extras) |

#### Presence extras
The following fields are stored in each of the [extras](#extras).

| Field | Description |
| --- | --- |
| appInfo:appId | Title id |
| appInfo:presenceGroupId | Title id |
| appField | JSON-encoded string |

#### Play log entry
| Field | Description |
| --- | --- |
| appInfo:appId | Title id |
| appInfo:presenceGroupId | Title id |
| totalPlayCount | Total play count |
| totalPlayTime | Total play time in minutes |
| firstPlayedAt | Timestamp |
| lastPlayedAt | Timestamp |

### GET /1.0.0/certificates
This method returns the JWK set for the id token that's issued by <code><a href="#post-100login">/1.0.0/login</a></code>.

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
| 400 | invalid_request | Authorization header value is invalid | Auth scheme or auth params is invalid |
| 400 | invalid_device_account | Invalid Device Account | Device Account's id or password is invalid |
| 400 | invalid_ndas_app_authn_token | Invalid NDAS App AuthN Token | |
| 400 | invalid_idp | ? | ? |
| 400 | invalid_idp_account | Invalid IdP Account | IdP account is invalid |
| 400 | linked_user_not_found | Linked User Not Found | linked user not found |
| 400 | invalid_friend_code_format | ? | ? |
| 400 | user_link_not_exist | ? | ? |
| 400 | invalid_raw_content | ? | ? |
| 401 | invalid_token | Token is invalid | The access token was invalid |
| 403 | insufficient_scope | ? | ? |
| 403 | forbidden | ? | ? |
| 403 | membership_required | Membership Required | |
| 403 | unavailable_device_account | Unavailable Device Account | Device Account is unavailable |
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