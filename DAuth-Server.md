[[Server List]] > DAuth Server
---

This server is at: https://dauth-lp1.ndas.srv.nintendo.net

Most Switch servers can only be accessed after acquiring a device authorization token from the dauth server. The dauth server only accepts requests with a valid client certificate. Every Switch has its own certificate, which stored in [PRODINFO](https://switchbrew.org/wiki/Calibration).

The dauth server takes form-encoded requests and responds with json-encoding. Also, this server uses the alternative base64 table (with '-' and '_' instead of '+' and '/'), and the client does not add any padding characters.

This page was last updated for firmware version 9.1.0.

## Headers
| Header | Description |
| --- | --- |
| User-Agent | `libcurl (nnDauth; 16f4553f-9eee-4e39-9b61-59bc7c99b7c8; SDK 9.3.0.0)` |
| X-Nintendo-PowerState | `FA` (fully awake) or `HA` (half awake) |

## Methods
| Method | URL |
| --- | --- |
| POST | <code><a href="#post-v6challenge">/v6/challenge</a></code> |
| POST | <code><a href="#post-v6device_auth_token">/v6/device_auth_token</a></code> |
| POST | `/v6/edge_token` |

### POST /v6/challenge
| Param | Description |
| --- | --- |
| key_generation | Master key revision (11) |

Response:

| Field | Description |
| --- | --- |
| challenge | Base64-encoded challenge |
| data | Base64-encoded AES key required for MAC calculation |

### POST /v6/device_auth_token
| Param | Description |
| --- | --- |
| challenge | Base64-encoded challenge |
| client_id | Application-specific client id |
| ist | `true` or `false` (depends on [platform region](https://switchbrew.org/wiki/Settings_services#GetT)) |
| key_generation | Master key revision (11) |
| system_version | [System version digest](https://switchbrew.org/wiki/System_Version_Title) |
| mac | Base64-encoded AES-CMAC of all previous fields in form-encoding |

Response on success:

| Field | Description |
| --- | --- |
| expires_in | Expiration in seconds (86400) |
| device_auth_token | Device authorization token |

The key for the AES-CMAC is calculated as follows:
1. The `aes_kek_generation_source` is decrypted with the master key.
2. The dauth key source is decrypted with the key from step 1.
3. The key from the `data` field of the challenge is decrypted with the key from step 2.

The dauth key source is: `8be45abcf987021523ca4f5e2300dbf0`

### Known Client IDs
| Client ID | Description |
| --- | --- |
| `8f849b5d34778d8e` | Account services |

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
| 0014 | Invalid parameter in request. |