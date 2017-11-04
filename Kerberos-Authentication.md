# Overview
When requesting a NEX token from the account server, one of the things the server returns is your NEX password. This password is never sent to the authentication server. Instead, it is used to generate the Kerberos key, by MD5-hashing the password `65000 + pid % 1024` times. The Kerberos key is used to decrypt the Kerberos ticket received from the authentication server, which contains the key that will be used in communication with the secure server, and the data that's sent to the secure server in the connection request.

# Kerberos Ticket
| Type | Description |
| --- | --- |
| Bytes | Secure key |
| Uint32 | Unknown |
| [Buffer] | Ticket data |

The length of the secure key is always 32 bytes, except in communication with the friends server, in which case it's 16 bytes.

## Kerberos Encryption
First, the data is encrypted with RC4 using the Kerberos key. Then a HMAC of the encrypted data (also using the Kerberos key) is appended to the data. The decryption process is basically the reverse: first check the HMAC, then decrypt using the Kerberos key.

[Buffer]: NEX-Common-Types#buffer