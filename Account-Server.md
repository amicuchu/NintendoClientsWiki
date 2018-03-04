## Overview
The account server uses HTTP requests with XML body.

The Wii U's client certificate is needed to connect to these servers.

Main server: https://account.nintendo.net

Other servers:
* https://game-dev.account.nintendo.net
* https://system-dev.account.nintendo.net
* https://library-dev.account.nintendo.net
* https://staging.account.nintendo.net

## Headers
The following headers are included in requests by the Wii U:

| Field | Description |
| --- | --- |
| X-Nintendo-Platform-ID | Always 1? |
| X-Nintendo-Device-Type | 1=Debug, 2=Retail |
| X-Nintendo-Device-ID | Unsigned integer (MCP_GetDeviceId) |
| X-Nintendo-Serial-Number | String |
| X-Nintendo-System-Version | Integer |
| X-Nintendo-Region | 1=JPN, 2=USA, 4=EUR, 8=AUS, 16=CHN, 32=KOR, 64=TWN |
| X-Nintendo-Country | JP for Japan, DE for Germany, etc. |
| X-Nintendo-Client-ID | a2efa818a34fa16b8afbc8a74eba3eda |
| X-Nintendo-Client-Secret | c91cdb5658bd4954ade78533a339cf9a |
| X-Nintendo-FPD-Version | Always "0000"? |
| X-Nintendo-Environment | Lx/Dx/Sx/Tx/Jx (default: L1) |
| X-Nintendo-Title-ID | Example: 0005000010138300 |
| X-Nintendo-Unique-ID | Part of title id, example: 01383 |
| X-Nintendo-Application-Version | Title version |

## Requests
The base path of each request is /v1/api, a valid url would be for example https://account.nintendo.net/v1/api/admin/mapped_ids.

Here's an example error response:
```
<errors>
  <error>
    <cause>client_id</cause>
    <code>0004</code>
    <message>API application invalid or incorrect application credentials</message>
  </error>
</errors>
```

### GET /admin/time

### GET /admin/mapped_ids
Converts between PID and NNID.

| Param | Description |
| --- | --- |
| input_type | "pid" or "user_id" |
| output_type | "pid" or "user_id" |
| input | comma-separated list |

Example response:
```
<mapped_ids>
  <mapped_id>
    <in_id>Kinnay-WiiU</in_id>
    <out_id>1798037410</out_id>
  </mapped_id>
</mapped_ids>
```

### GET /content/agreements/Nintendo-Network-EULA/&lt;country&gt;/@latest
| Param | Description |
| --- | --- |
| length | Maximum response length |

### GET content/time_zones/&lt;country&gt;/&lt;language&gt;

### POST /devices/@current/migrations

### DELETE /devices/@current/migrations

### POST /devices/@current/migrations/commit

### GET /devices/@current/status

### GET /miis

### POST /oauth20/access_token/generate
This method generates an access token. The access token can be included in the "Authorization" header, and is needed for all requests that require access to your account data.

There are two ways to request an access token: using NNID and password or password hash, or using a refresh token from an earlier access token request.

The password hash can be calculated using the following method:
```
data = struct.pack("<I", pid) + b"\x02\x65\x43\x46" + password.encode("ascii")
hash = hashlib.sha256(data).hexdigest()
```

| Field | Description |
| --- | --- |
| grant_type | "password" |
| user_id | NNID |
| password | Password or password hash |
| password_type (optional) | "hash" |

| Field | Description |
| --- | --- |
| grant_type | "refresh_token" |
| refresh_token | Refresh token |

Example response:
```
<OAuth20>
  <access_token>
    <token>ee5cdb25b746aa3934a42516fec22369</token>
    <refresh_token>b9c1f1fd111883c88b11af5ecb2e65e025e532a1</refresh_token>
    <expires_in>3600</expires_in>
  </access_token>
</OAuth20>
```

### POST /people

### GET /people/@me

### GET /people/@me/devices

### DELETE /people/@me/devices/@current

### GET /people/@me/emails

### GET /people/@me/profile

### GET /provider/nex_token/@me

### GET /provider/service_token/@me

### POST /support/validate/email
