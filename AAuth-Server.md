[[Server List]] > AAuth Server
---

This server is at: https://aauth-lp1.ndas.srv.nintendo.net

The aauth server provides application authorization tokens. These are required to access game-specific servers, such as [NEX](NEX-Overview-(Game-Servers)).

This server takes form-encoded requests and responds with json-encoding. Also, this server uses the alternative base64 table (with '-' and '_' instead of '+' and '/')

## Headers
| Header | Description |
| --- | --- |
| User-Agent | [User agent](#user-agents) |
| X-Nintendo-PowerState | `FA` (fully awake) or `HA` (half awake). This header is only sent in the <code><a href="#post-v3application_auth_token">/v3/application_auth_token</a></code> request. |

#### User Agents
| System Version | User agent |
| --- | --- |
| 9.0.0 - 9.2.0 | `libcurl (nnAccount; 789f928b-138e-4b2f-afeb-1acae821d897; SDK 9.3.0.0; Add-on 9.3.0.0)` |
| 10.0.0 - 10.0.3 | `libcurl (nnAccount; 789f928b-138e-4b2f-afeb-1acae821d897; SDK 10.4.0.0; Add-on 10.4.0.0)` |

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

Response on success:

| Field | Description |
| --- | --- |
| value | Base64-encoded (16 bytes) |
| seed | Base64-encoded (15 bytes) |

### POST /v3/application_auth_token
The following parameters are always present:

| Param | Description |
| --- | --- |
| application_id | Title id (`%016x`) |
| application_version | Title version (`%08x`) |
| device_auth_token | Device token from [dauth server](DAuth-Server) |
| media_type | `GAMECARD`, `DIGITAL`, `SYSTEM` or `NO_CERT` |

The following parameters depend on the media type of the game:

#### GAMECARD
| Param | Description |
| --- | --- |
| gvt | Base64-encoded challenge reply, based on the seed and value from <code><a href="#post-v3challenge">/v3/challenge</a></code> (88 bytes) |
| cert | Base64-encoded gamecard certificate (stored on game card itself) |

#### DIGITAL
The certificate is read from ES save data (`escommon` or `espersonalized`). First the index of the ticket is looked up in `ticket_list.bin` by rights id. Then the certificate itself is read from `ticket.bin`.

The ticket is not sent to the server in plain text. Instead, it is encrypted with AES-CBC with a random key. The key itself is then encrypted with RSA-OAEP with SHA256.

| Param | Description |
| --- | --- |
| cert | Encrypted certificate (base64) |
| cert_key | Encrypted key (base64) |

Public exponent: `65537`

Public modulus:
```
2903599220185509629948246004681271806662185201109683699434876284
9306378942456577312580648895443616535088601867223713942187399041
4854872772034425863387471719375473684104853507768450203982749294
8967945831738920699512732919046223059402955082098739033920491649
6879108565068863591362496844602988110766097564477545097467537357
3183749964356608012071405755940871989007021731074728723470759285
8155278592486462922448753256166071381157786436864032235809243318
2591089355065715995209202752330511548478896205428626608544326862
4782505679727111312756904637828438785474471375120478991907979820
98870089661523253199182993983393803812441
```

#### Response on success:

| Field | Description |
| --- | --- |
| expires_in | Expiration in seconds (86400) |
| application_auth_token | Application authorization token |
| settings | Unknown (list) |
| online_play_policy | `MEMBERSHIP_REQUIRED` or `FREE` |
| policy_handler | `SYSTEM` or `GAME_SERVER` |

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
| Code | Dialog | Message |
| --- | --- | --- |
| 0103 | 2124-4603 | ? |
| 0105 | 2124-4605 | ROM ID has been banned. |
| 0106 | 2124-4606 | ? |
| 0107 | 2124-4607 | ? |
| 0108 | 2124-4608 | ? |
| 0109 | 2124-4609 | ? |
| 0110 | 2124-4610 | ? |
| 0111 | 2124-3001 | Application update is required. |
| 0112 | 2124-4612 | ? |
| 0113 | 2124-4613 | ? |
| 0118 | 2124-4618 | Invalid parameter in request. |
| 0120 | 2124-4620 | ? |
| 0121 | 2124-4621 | ? |