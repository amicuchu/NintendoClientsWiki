[[Server List]] > DAuth Server
---

This server is at: https://dauth-lp1.ndas.srv.nintendo.net

Most Switch servers can only be accessed after acquiring a device authorization token from the dauth server. The dauth server only accepts requests with a valid client certificate. Every Switch has its own certificate, which stored in [PRODINFO](https://switchbrew.org/wiki/Calibration).

The dauth server takes form-encoded requests and responds with json-encoding. Also, this server uses the alternative base64 table (with '-' and '_' instead of '+' and '/'), and the client does not add any padding characters.

## Headers
| Header | Description |
| --- | --- |
| User-Agent | [User agent](#user-agents) |
| X-Nintendo-PowerState | `FA` (fully awake) or `HA` (half awake) |

#### User Agents
| System Version | User agent |
| --- | --- |
| 9.0.0 - 9.2.0 |  `libcurl (nnDauth; 16f4553f-9eee-4e39-9b61-59bc7c99b7c8; SDK 9.3.0.0)` |
| 10.0.0 | `libcurl (nnDauth; 16f4553f-9eee-4e39-9b61-59bc7c99b7c8; SDK 10.4.0.0)` |

## Methods
| Method | URL |
| --- | --- |
| POST | <code><a href="#post-v6challenge">/v6/challenge</a></code> |
| POST | <code><a href="#post-v6device_auth_token">/v6/device_auth_token</a></code> |
| POST | `/v6/edge_token` |

### POST /v6/challenge
| Param | Description |
| --- | --- |
| key_generation | [Master key revision](#master-key-revisions) |

Response:

| Field | Description |
| --- | --- |
| challenge | Base64-encoded challenge |
| data | Base64-encoded AES key required for MAC calculation |

### POST /v6/device_auth_token
| Param | Description |
| --- | --- |
| challenge | Base64-encoded challenge |
| client_id | Application-specific [client id](#known-client-ids) |
| ist | `true` or `false` (depends on [platform region](https://switchbrew.org/wiki/Settings_services#GetT)) |
| key_generation | [Master key revision](#master-key-revisions) |
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

### Master Key Revisions
| System version | Key generation |
| --- | --- |
| 9.0.0 - 9.0.1 | 10 |
| 9.1.0 - 10.0.0 | 11 |

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
| Code | Dialog | Message |
| --- | --- | --- |
| 0000 | 2181-0100 | ? |
| 0001 | 2181-0100 | ? |
| 0002 | 2181-0100 | ? |
| 0003 | 2181-0100 | ? |
| 0004 | 2181-4004 | ? |
| 0005 | 2181-0100 | ? |
| 0006 | 2181-0100 | ? |
| 0007 | 2181-4007 | ? |
| 0008 | 2181-4008 | Device has been banned. |
| 0009 | 2181-4009 | ? |
| 0010 | 2181-4010 | ? |
| 0011 | 2181-4011 | ? |
| 0012 | 2181-0100 | ? |
| 0013 | 2181-4013 | ? |
| 0014 | 2181-4014 | Invalid parameter in request. |
| 0015 | 2181-4015 | ? |
| 0016 | 2181-4016 | ? |
| 0017 | 2181-4017 | ? |
| 0018 | 2181-4018 | ? |
| 0019 | 2181-4019 | ? |
| 0020 | 2181-4020 | ? |
| 0021 | 2181-4021 | ? |
| 0022 | 2181-4022 | ? |
| 0023 | 2181-4023 | ? |
| 0024 | 2181-4024 | ? |
| 0025 | 2181-4025 | ? |
| 0026 | 2181-4026 | ? |
| 0027 | 2181-4027 | ? |
| 0028 | 2181-4028 | ? |
| 0029 | 2181-4029 | ? |
| 0030 | 2181-4030 | ? |
| 0031 | 2181-4031 | ? |