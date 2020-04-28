Many Switch servers use JWTs (json web tokens) for authentication. JWTs are a simple and standardized way to pass information between servers without storing it in a database. A JWT consists of three parts separated by dots, and each part is encoded with the url-safe base64 table ('-' and '_' instead of '+' and '/').

JWTs are described formally in [RFC 7515](https://tools.ietf.org/html/rfc7515), [RFC 7518](https://tools.ietf.org/html/rfc7518) and [RFC 7519](https://tools.ietf.org/html/rfc7519).

Details on specific kinds of token:
* [Device auth tokens](#dauth-tokens)
* [Application auth tokens](#aauth-tokens)
* [BaaS session tokens](#baas-session-tokens)
* [ID tokens](#id-tokens)

### Header
The first part contains information about the JWT itself, such as the signature algorithm that's used.

| Field | Description |
| --- | --- |
| `jku` | **JWK Set URL:** The URL of a server that provides a [JWK set](#jwk-set). This server provides the public keys that are used to verify the signature in the JWT. |
| `kid` | **Key ID:** The key id in the JWK set provided by the `jku` server. This is a uuid v4 on Nintendo's servers. |
| `alg` | **Algorithm:** Always `RS256`. |
| `typ` | **Type:** Always `JWT`. Not present in tokens returned by baas server. |

Example:

```json
{
  "jku":"https://dcert-lp1.ndas.srv.nintendo.net/keys",
  "kid":"2567fb65-eacb-48ba-9eb0-ed815a9f1a06",
  "typ":"JWT",
  "alg":"RS256"
}
```

### Payload
The second part contains a set of "claims": the information that's stored in the JWT, such as the user id. The content of the payload depends on the type of token, but the following fields are always present:

| Field | Description |
| --- | --- |
| `sub` | **Subject:** An id that identifies what the JWT is about, such as a user id. |
| `exp` | **Expiration Time:** A timestamp that specifies the expiration date of the JWT. |
| `iat` | **Issued At:** A timestamp that specifies the time at which the token was generated. |
| `iss` | **Issuer:** The server that generated the JWT. |
| `jti` | **JWT ID:** A unique id per generated JWT. |

### Signature
The third part contains the signature. This prevents the JWT from being modified by anyone. Nintendo uses the RS256 algorithm everywhere, which is formally called RSASSA-PKCS1-v1_5.

The signature is calculated over both the [header](#header) and the [payload](#payload) in base64-encoded form with a dot in between. Only the server can generate the signature, because only the server knows the private keys. Anyone can verify the signature though, because anyone can download the public keys from the server that hosts the JWK set.

### JWK Set
The JWK set contains a set of public keys that can be used to verify the [signature](#signature) of the JWT. It's hosted by the server that's specified in the `jku` field in the [header](#header).

Each JWK contains the following fields:

| Field | Description |
| --- | --- |
| `kty` | **Key Type:** Always `RSA`. |
| `e` | **Exponent:** The public exponent of the RSA key. |
| `n` | **Modulus:** The public modulus of the RSA key. |
| `alg` | **Algorithm:** Always `RS256`. |
| `use` | **Public Key Use:** Always `sig`. |
| `kid` | **Key ID:** A unique id that identifies the key. This id is also specified in the [JWT header](#header). |

`e` and `n` are encoded with the url-safe base64 table.

The baas server also returns the following fields:

| Field | Description |
| --- | --- |
| `usage` | `developer` or `internal` |
| `x5c` | X.509 Certificate Chain |

JWKs are described formally in [RFC 7517](https://tools.ietf.org/html/rfc7517) and [RFC 7518](https://tools.ietf.org/html/rfc7518).

## DAuth Tokens
| Field | Value |
| --- | --- |
| `jku` | https://dcert-lp1.ndas.srv.nintendo.net/keys |
| `kid` | `2567fb65-eacb-48ba-9eb0-ed815a9f1a06` |

<details><summary>JWK set (click to show)</summary>

```json
{
  "keys": [
    {
      "kty": "RSA",
      "e": "AQAB",
      "n": "upUROmsdoSEnbste9i0UDc2myVZBgd-YwAx_5oahwmaByq516fEzRSwnYyVOX_6Ni6rQQ8WvAUTXgIVsOl3bLHnIoYHFzzO1iBUNRCvrECjQS0oC73kA6aFHN--uIjgrLXsaeatbuFILLGCsnKVNYpweleZQtzh3ISBwscPo_xhs1GBxFBHpRXOxr7i1Rbtm-r2j0Dc2ATjVg4NxWKcRJ_LI-RBWqgb_QTungedwLJ_bhYq8UHzpWwpr5Tc9NH7swvxX1hifSDMhiZFRzXceLUTIpLzn16nhG_2nLMUqilfXUDYLr_eMGcIQCD5AezsrClFtYI4St6iFxjZ5PMqa2Q",
      "alg": "RS256",
      "use": "sig",
      "kid": "942401dc-8828-4cae-a20f-85c017c97301"
    },
    {
      "kty": "RSA",
      "e": "AQAB",
      "n": "qjk1pMUDyvMkomlEYuYJf-z1bF7HBl4x5YfWOW0lBTj0BYI2eDH7esMmUq0BOu8wU2dgIlWrqtcRHaBn0csiXUxX1BDZP3mJEh-6llvKdcc96wwo8LjPMSY3_CDnuNRYWC99TwMALkBv_UJ8oz9l60ksU8FNsrLdbRye_KrIqtshL-2g6pGHXbtBxkVjHCKd5SynEQ79llQmIfNo6YSSO7g2SQLRVbVKnaIAT1jzfG7JB9Xs5sWU6YrDf4zLakaO3avU8l7LyawKE58hoUAfCNXIgOve4ge2tmpLnbul2bpJuJ0DAPeu6lqMJjrCKS5sRSt_7BtytpnL3WvsHzBkhw",
      "alg": "RS256",
      "use": "sig",
      "kid": "2567fb65-eacb-48ba-9eb0-ed815a9f1a06"
    },
    {
      "kty": "RSA",
      "e": "AQAB",
      "n": "9_972w056UFjQD4V4FGv_daxmMB8cYHyFrKcClPez6F508t_kdUJpwBpcdP8pIvh2PrqH4hVFvGnUM8mseSAodOTHi8fn4DwAom-3WBGOj-gmrMwR3aGFNCzYWSsjCovKO3HHjTulMfNMzGaq-AdbGkUo3XSZY_Ukcg-0nVe8ctS_I-rRe24rKuphpsJSQUT6cBVCijuiixq4O6yLMXHHe52uGbyJEarW-LrAF0cbF_zoQurElUiAhTuTX8zmTPese0FVdSLYkrA3_U2lhoSEmNFTn470rq9fB_U9fkKhQaOqK_OMv_CjToctFaaCDMPbpD9-onD5YrQTc_eNGK2hQ",
      "alg": "RS256",
      "use": "sig",
      "kid": "4eb067f1-fd36-4dd5-8625-fdf537dfd141"
    }
  ]
}
```
</details>

Payload fields:

| Field | Description |
| --- | --- |
| `sub` | Device id |
| `iss` | dauth-lp1.ndas.srv.nintendo.net |
| `aud` | Client id |
| `nintendo` | [Device information](#device-information) |

### Device Information
| Field | Description |
| --- | --- |
| `sn` | Serial number |
| `pc` | Product code: `HAC` |
| `dt` | Device type: `NX Prod 1` |
| `ist` | IsT (bool) |

## AAuth Tokens
| Field | Value |
| --- | --- |
| `jku` | https://acert-lp1.ndas.srv.nintendo.net/keys |
| `kid` | `13e1e19b-2b3c-4dec-99aa-1a99c228990c` |

<details><summary>JWK set (click to show)</summary>

```json
{
  "keys": [
    {
      "kty": "RSA",
      "e": "AQAB",
      "n": "tbGdiNemBGFMZExxlfVoYFUS7k_FwN_B8aHh8acFtfBG-TFVpjc1SLmTqyaIFn3PQfVyfQCdRXya8W-gDT-4RSqLvdA65EXXtTp8px6MYn-Zbvl8kYxeZ3-8_neirKbIC_TGrpwIJTu1gm5j5A2zgnVY6iSs_EHCy4e2dDIBsP8hyNkDRzm9vI3n87SejgcGJ3tsNt1Akms0JHmcA4Iqbhei5xKYHzpCe-3Gs9c93inX4Z54E7wtXIyOUy1w7u9-fnI6JZ3Rtu0iPj715A6ADw5UtIWoiySgQU6foNomzYjyXxZmyS_ZJF1Elqfmc6fXB7Bl0oklyH_dNHPfPDUFNw",
      "alg": "RS256",
      "use": "sig",
      "kid": "28bca78d-ed7e-48da-a661-bd9a98289554"
    },
    {
      "kty": "RSA",
      "e": "AQAB",
      "n": "vuCKoMOFAGB31K9wfJYy6a24aC9odmWK1fg5Sg-naP3CQpc8r29R4SNgzZoD4t4GXokHVHGQSrir-7sC_d1PB2HT7cmqQWNmToGGaa-OGd6OF1Us5E-G7zL05GLFX3DZg1iRDEB1xm6-Hh_y1DG_4NU3tgubi5AWCV4PSDX7qeuIb2fmIKAZusPxH18oLLpLCc1prXo0pFnHdpDql5UNyAK3dTgcdUQzgEkXheKdkjuGmY9W-PJMH23oJSvi1NVGv_7x_txzSk8QzLWzQX1d9j_MlaICDggTiOiairMoeJDadtVDEfg9jcuj6Mk2fMx5Zh0jKaeKcUpfzncwgrZmyw",
      "alg": "RS256",
      "use": "sig",
      "kid": "13e1e19b-2b3c-4dec-99aa-1a99c228990c"
    },
    {
      "kty": "RSA",
      "e": "AQAB",
      "n": "uONds3-rFMdJchyWxjem62K1TiqQDUE5kI8HabsJ6cLjsK2er2FJXasCiMT6H572AmEpWbDylBUJV2WUVyGtAeGM3z5JjwcTtfPT5u9gSb4G8wMM1nEdxHsVsuaH6fln5dvtgp1eWO_c5haKwCRjh3ZqXfDA9z-LPrSE4sJeEgPt6hKcWT471uoH4Vbiv3zeeyPCKHEC9StaDGPFXHNibdX9mBsUTyjRExYSQ55pGq2oFEm87Wtz2y7mkOWD6MT4aTrMgNuzm9lqHEs7TJoW19JJfdGQRRQRnLjR46Mh5cAVh9B5J2EfyRCgrCKuTc9WArLUtzij6_dFylCFuT1P5Q",
      "alg": "RS256",
      "use": "sig",
      "kid": "7fbae6ae-49d0-486e-be6b-c5ad7bccc57c"
    }
  ]
}
```
</details>

Payload fields:

| Field | Description |
| --- | --- |
| `sub` | Title id (`%016x`) |
| `iss` | aauth-lp1.ndas.srv.nintendo.net |
| `nintendo` | [Application information](#application-information) |

### Application Information
| Field | Description |
| --- | --- |
| `ai` | Application id (`%016x`) |
| `av` | Application version (`%04x`) |
| `at` | Application time (current timestamp) |
| `edi` | Unique id (32 hex digits) |
| `opp` | Online play policy: `MEMBERSHIP_REQUIRED` or `FREE` |
| `ph` | Policy handler: `SYSTEM` or `GAME_SERVER` |

## BaaS Session Tokens
| Field | Value |
| --- | --- |
| `jku` | https://e0d67c509fb203858ebcb2fe3f88c2aa.baas.nintendo.com/1.0.0/internal_certificates |
| `kid` | `3083c1b2-5d68-434b-be32-11f915570500` |

<details><summary>JWK set (click to show)</summary>

```json
{
  "keys": [
    {
      "kty": "RSA",
      "use": "sig",
      "alg": "RS256",
      "kid": "3083c1b2-5d68-434b-be32-11f915570500",
      "usage": "internal",
      "n": "8Cn3PfASZ_yF1XFZpGucwaRtxZUPsDTuq8WM2yTvB9pIOdP7dePd_O0_-TloEdAJa6hJwFqBdjp3NcBwu3pWfqUBTr69muULi5ZFh-krlkpYJWsUTM_wEcnnSG96B4HqPP--wn5MnxlsNi6pZRysi_UNOfq4GuFqOSZTXJe-kLDb8IiMQogd4SZNS_IF23tjycRnuKmXceUasNXptzO6LWs7t9D9yIc8IL960RnZVPu5uJD7V5998Lwh_wIp8VK7DiW8X9fMPwA08kXAk4JAkq9Y9H58t2v5NX-hMaEK2iRpVbiZM4eoaQBcFhX67WCLHMU6iMK3uvgvPWnYlTgLdQ",
      "e": "AQAB",
      "x5c": [
        "MIICuTCCAaGgAwIBAgIHBUF8hd6nbzANBgkqhkiG9w0BAQUFADAdMRswGQYDVQQDExIuYmFhcy5uaW50ZW5kby5jb20wHhcNMTUxMTE4MDAwMDAwWhcNMTcxMTE3MDAwMDAwWjAdMRswGQYDVQQDExIuYmFhcy5uaW50ZW5kby5jb20wggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDwKfc98BJn/IXVcVmka5zBpG3FlQ+wNO6rxYzbJO8H2kg50/t149387T/5OWgR0AlrqEnAWoF2Onc1wHC7elZ+pQFOvr2a5QuLlkWH6SuWSlglaxRMz/ARyedIb3oHgeo8/77CfkyfGWw2LqllHKyL9Q05+rga4Wo5JlNcl76QsNvwiIxCiB3hJk1L8gXbe2PJxGe4qZdx5Rqw1em3M7otazu30P3Ihzwgv3rRGdlU+7m4kPtXn33wvCH/AinxUrsOJbxf18w/ADTyRcCTgkCSr1j0fny3a/k1f6ExoQraJGlVuJkzh6hpAFwWFfrtYIscxTqIwre6+C89adiVOAt1AgMBAAEwDQYJKoZIhvcNAQEFBQADggEBAKH9cGhvmj5O+SFKQdw15I+Jxl7vBhUX2lH1Ds0n4WXqtqopv2QCJfBu0r7ZHCkF2QWzQzoR54nO6SUsd8DaL3gVpsahhCAHRMS8Tm78pNoBUdY6wuJjRmeMa/b250gz1csjIs7/YiujM3KXhRlWtY/yIo1eprrtiJ/pE+H0Z3n4phEYyycQ6Rd6COVL3f7c6thg9tTMH5TxcIPDTYkFVppspXGQTMO6RJjnP1xBZtXIjvSJqPC9gcuQ8Q87m+YGrgxxm/wGhfO6Mc2dAwkDVep3C5JsKcxSQcLctX0wzS4iXx2/BB92A/sYAqNF5kk7RxNnVA4br6PaIxCe4tBGjKo="
      ]
    }
  ]
}
```
</details>

Payload fields:

| Field | Description |
| --- | --- |
| `sub` | Client id? |
| `aud` | Client id? |
| `bs:sts` | Always [385]? (list) |
| `nintendo` | [Device information](#device-information-0) |
| `iss` | https://e0d67c509fb203858ebcb2fe3f88c2aa.baas.nintendo.com |
| `typ` | Always `token` |
| `bs:grt` | Always 1? |

### Device Information
| Field | Description |
| --- | --- |
| `dt` | Device type: `NX Prod 1` |
| `pc` | Product code: `HAC` |
| `di` | Device id |
| `sn` | Serial number |
| `ist` | IsT (bool) |

## ID Tokens
| Field | Value |
| --- | --- |
| `jku` | https://e0d67c509fb203858ebcb2fe3f88c2aa.baas.nintendo.com/1.0.0/certificates |
| `kid` | `b99d46d3-1568-4f08-9597-111b481eccae` |

<details><summary>JWK set (click to show)</summary>

```json
{
  "keys": [
    {
      "kty": "RSA",
      "use": "sig",
      "alg": "RS256",
      "kid": "7134708f-3f86-4a62-b433-e97e11a8c10a",
      "usage": "developer",
      "n": "mOdC13iqB_AqfbAQ7aD63i6i9KQNxdeBx8kNsqyneuou-g7-r-bOPqKpsIdl8GDae-imofbWjvIhFEmE9BVAv_brSJf7sjY5QJaMFTzjyayHtpV7GazXVI5FO0qk5yb8Dj-hhHKoOznst6hBAv5DYWFNY7GtwJSCxRGxu8VFAMrc1t9J2IPAvFG31p93Il46MCLVYpKJEUfg-E22BFw-RYPQ2MpqCe5VKqFt2Vm2M1-wLZbLNxTImYwwXl2EGoEaDdzmOHrDxOEpfgdyAUwodT6GS_pW6_awsvZiOXzqRyftOpTZ-fg0ZyAvRACr4s6flyGgnAChiIaSFdm68kDQUQ",
      "e": "AQAB",
      "x5c": [
        "MIIC+TCCAeGgAwIBAgIHBaREwwuZkDANBgkqhkiG9w0BAQUFADA9MTswOQYDVQQDDDJlMGQ2N2M1MDlmYjIwMzg1OGViY2IyZmUzZjg4YzJhYS5iYWFzLm5pbnRlbmRvLmNvbTAeFw0xOTA0MjgwNjMzMTBaFw0yMTA0MjcxODEwNTBaMD0xOzA5BgNVBAMMMmUwZDY3YzUwOWZiMjAzODU4ZWJjYjJmZTNmODhjMmFhLmJhYXMubmludGVuZG8uY29tMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAmOdC13iqB/AqfbAQ7aD63i6i9KQNxdeBx8kNsqyneuou+g7+r+bOPqKpsIdl8GDae+imofbWjvIhFEmE9BVAv/brSJf7sjY5QJaMFTzjyayHtpV7GazXVI5FO0qk5yb8Dj+hhHKoOznst6hBAv5DYWFNY7GtwJSCxRGxu8VFAMrc1t9J2IPAvFG31p93Il46MCLVYpKJEUfg+E22BFw+RYPQ2MpqCe5VKqFt2Vm2M1+wLZbLNxTImYwwXl2EGoEaDdzmOHrDxOEpfgdyAUwodT6GS/pW6/awsvZiOXzqRyftOpTZ+fg0ZyAvRACr4s6flyGgnAChiIaSFdm68kDQUQIDAQABMA0GCSqGSIb3DQEBBQUAA4IBAQBs0lVLeOTCYbTVOQafuDVjEdlLa/TOLS9rOBzzxOjHOFg9M14JpCzFLPAoTto74TtTqiGC2Cb8ae4dEar/Tj6QvFAs/95KAuIXRefLXyo4DEa+7z/5yB2j1uj2qSPlaaSEmA8SoqlrZlJ8PFwJKCqiTacouH59TENsliwHbcBB1U/aa8of9HYzJpsqcZZZYe6oURN54XOealrVBfJbGh/yvy7aZ2icFd2r1WbmMnrHnk48Dyzb5ZXC6r+0sKymK/enXW192CPuofw22yKmZYhusiTiSPHmJm+IMEELQuBVt8yqcGNy+sm4akxzhj3k+wmrKG3wCajXSKrAgOOZ1eau"
      ]
    },
    {
      "kty": "RSA",
      "use": "sig",
      "alg": "RS256",
      "kid": "b99d46d3-1568-4f08-9597-111b481eccae",
      "usage": "developer",
      "n": "x0JWZ2Zeq1-vvdLbdubtJq7U0OpzTXVayAzNVIEGqM04qxSJprUrlaPYGoBKxhAbUKzvmqKFBSOq5v9Eqx4EUi-CbR5JyCcFMpR69ZdkM0Jjc1CrG-QAhLb2fzratuGtzuoOzM_beMBg1ZGv0oHtQFW0WLP0J_vjM-689ypGg-AgAhvRhX7_id9xP-SeAOGp-FB5pES9HoHjy94ego_n7c-qHjeYNrm1dcqmEaYs-mtolLCfSXGRCtTjP9PdSZFA9To26SQjjzE1738NLERwUdqSOyOL5bniUz2Fug59FpQ3hhVwvYORY_yWpE3I3xqgOd9EcW1ZRzOenfedLMMZAQ",
      "e": "AQAB",
      "x5c": [
        "MIIC+TCCAeGgAwIBAgIHBaQwoaV9IDANBgkqhkiG9w0BAQUFADA9MTswOQYDVQQDDDJlMGQ2N2M1MDlmYjIwMzg1OGViY2IyZmUzZjg4YzJhYS5iYWFzLm5pbnRlbmRvLmNvbTAeFw0xOTA0MjcwNjMyMTBaFw0yMTA0MjYxODA5NTBaMD0xOzA5BgNVBAMMMmUwZDY3YzUwOWZiMjAzODU4ZWJjYjJmZTNmODhjMmFhLmJhYXMubmludGVuZG8uY29tMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAx0JWZ2Zeq1+vvdLbdubtJq7U0OpzTXVayAzNVIEGqM04qxSJprUrlaPYGoBKxhAbUKzvmqKFBSOq5v9Eqx4EUi+CbR5JyCcFMpR69ZdkM0Jjc1CrG+QAhLb2fzratuGtzuoOzM/beMBg1ZGv0oHtQFW0WLP0J/vjM+689ypGg+AgAhvRhX7/id9xP+SeAOGp+FB5pES9HoHjy94ego/n7c+qHjeYNrm1dcqmEaYs+mtolLCfSXGRCtTjP9PdSZFA9To26SQjjzE1738NLERwUdqSOyOL5bniUz2Fug59FpQ3hhVwvYORY/yWpE3I3xqgOd9EcW1ZRzOenfedLMMZAQIDAQABMA0GCSqGSIb3DQEBBQUAA4IBAQCjeGYvVR4QX5YdY8lPdFb0/6xdFWfAfbpfoR+UzqHCezL1pnNmFKfsNHM7AF6KojrEoNF1sAb1uw88kXHadFi6ADLOv4f/SVpRPVf8K/u5AcFJcgbdbxG2h+JnDklC4g089pUrwjo8AqgTea3C8bw9lQ1BsCiUwUKk3Y3H3pCw0egiWJVLLkRCdBnIFN7e/2nrS8DLYl4BhsivKF9Mc5tsQO+yrnLt6tyNFMENEsZ4xZX/zy3Wz/L+xT1c9rpXnNn/8Do4DPEMEH8lyYKIX2PmABfMF0UISDiHcNjARo1qDEnhQEzzxm/Poiza70eVsE4Eg/q/uxtjbXVfVoxOfSyi"
      ]
    },
    {
      "kty": "RSA",
      "use": "sig",
      "alg": "RS256",
      "kid": "d0f4b051-397c-4c82-add1-ce71c8a9e432",
      "usage": "developer",
      "n": "i-LiIWjCKAAf1WbjpyiYKXm8IJRSsApI9ZPQk8h59dAdt8KbL6NBjXB2UnMAVvEr0N5hz_rgXONgDXQDNIelFZPiHqblKIe2165rPKV7v7GmZU_wa6zjcWqCLr9BNEMfNeOllzrxMGXAuTAIjLdbr8Imaxd7FU1Y24MN_RD5RTheGe5ZsgEOh8WCMz13qSpS4sjBTBamasXfCanMFzKk6jGikhEp2W0eRXHTGrQmDljh0e320UceudjmwMzjTRBG1xJwp3CLKteJbyyCZ72jGXFsQKLI2DsEHA3IV5Ma52O0Q5kVTiZaFJ0RfosKG-FKeW1hSpb10Jsh25R5ZZDydQ",
      "e": "AQAB",
      "x5c": [
        "MIIC+TCCAeGgAwIBAgIHBaRY5HGHIDANBgkqhkiG9w0BAQUFADA9MTswOQYDVQQDDDJlMGQ2N2M1MDlmYjIwMzg1OGViY2IyZmUzZjg4YzJhYS5iYWFzLm5pbnRlbmRvLmNvbTAeFw0xOTA0MjkwNjM0MTBaFw0yMTA0MjgxODExNTBaMD0xOzA5BgNVBAMMMmUwZDY3YzUwOWZiMjAzODU4ZWJjYjJmZTNmODhjMmFhLmJhYXMubmludGVuZG8uY29tMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAi+LiIWjCKAAf1WbjpyiYKXm8IJRSsApI9ZPQk8h59dAdt8KbL6NBjXB2UnMAVvEr0N5hz/rgXONgDXQDNIelFZPiHqblKIe2165rPKV7v7GmZU/wa6zjcWqCLr9BNEMfNeOllzrxMGXAuTAIjLdbr8Imaxd7FU1Y24MN/RD5RTheGe5ZsgEOh8WCMz13qSpS4sjBTBamasXfCanMFzKk6jGikhEp2W0eRXHTGrQmDljh0e320UceudjmwMzjTRBG1xJwp3CLKteJbyyCZ72jGXFsQKLI2DsEHA3IV5Ma52O0Q5kVTiZaFJ0RfosKG+FKeW1hSpb10Jsh25R5ZZDydQIDAQABMA0GCSqGSIb3DQEBBQUAA4IBAQBUitITdvES8bNJnsv0XhqYSi8cG4xttW0Vx7GMjtfBKZD6GzxiTG0/znPMIU1bj/2qTOA08gcqZKDioqK0calNn7cEBe5xOHvx7qqhtdk8g5RRZ8PoxDWARHzYLm3pe2JdJTuGd/ISvz3lVo9DB2BxweUF0ncvQv11tYB+qWLpg2Qcf/0K6N27MkVsdlJLSMNGKKXJXcHhyVnfYPoTUdjYVSwj/Rgksd4z/87mTEHin9jj8U/nogbDz5WTVH5KCAFxHECTjti1RpNZtormCMVQNq069WDc5pPFln4filF6xtMqoHXWny3fhGV7ffe20+0I/jEeENDCfIrwPS7RSkwE"
      ]
    }
  ]
}
```
</details>

Payload fields:

| Field | Description |
| --- | --- |
| `aud` | Client id? |
| `sub` | NEX user id (pid) |
| `iss` | https://e0d67c509fb203858ebcb2fe3f88c2aa.baas.nintendo.com |
| `nintendo` | [ID token information](#id-token-information) |
| `typ` | Always `id_token` |
| `bs:did` | BaaS device account id (`%016x`) |

### ID Token Information
| Field | Description |
| --- | --- |
| `ai` | Application id (`%016x`) |
| `av` | Application version (`%04x`) |
| `at` | Application time (current timestamp) |
| `edi` | Unique id (32 hex digits) |
