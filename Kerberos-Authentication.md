This page describes how user authentication works on game servers.

Before reading this page, make sure you have a basic understanding of how the game servers work in general.

# Overview
As explained on the [game server overview](NEX-Overview-(Game-Servers)) page, every game server has an authentication server and a secure server.

The authentication server only provides a single service: the [authentication service](Authentication-Protocol). To log in on a game server, you first need to know your username and password. These are obtained in a platform-specific way. Game server accounts are separate from other Nintendo accounts. Username and password are generated automatically and can not be changed by normal users.

<table>
  <tr>
    <td><b>3DS</b></td><td>Username and password are requested from the account server (when a NNID is linked), or from the NASC server the first time you go online without NNID.</td>
  </tr>
  <tr>
    <td><b>Wii U</b></td><td>Username and password are requested from the [[account server]] (/provider/nex_token/@me)</td>
  </tr>
  <tr>
    <td><b>Switch</b></td><td>Normal user accounts don't have a password anymore. Instead, they must provide an id token to log in. This token (and your username) can be retrieved by logging in on the <a href="BAAS-Server">BAAS server</a> after acquiring a <a href="DAuth-Server">device token</a> and an <a href="AAuth-Server">application token</a>.</td>
  </tr>
</table>

There's also a bunch of [special accounts](Authentication-Protocol#4-getpid) on all game servers.

### Basic authentication
To log in on the secure server, one of the login-related methods must be called on the [authentication service](Authentication-Protocol). The response should contain the location of the secure server and an encrypted ticket. The ticket must be sent to the secure server during connection establishment. This is how the secure server knows who is connecting.

On 3DS and Wii U servers, authentication is password-based (see [password authentication](#password-authentication)). On Switch servers, users must provide an id token to log in (see [authentication with token](#authentication-with-token)).

### Kerberos tickets
Not every ticket actually lets you log in on the secure server. Every ticket has a **source user** and a **target user**.

The **source user** is normally the user that requested the ticket, i.e. the user that wants to log in. The **target user** is the user that you want to connect to. Both the authentication server and the secure server have a special user account, and the **target user** is normally the user account of the secure server. If this seems weird, imagine that you are connecting to another user and this user happens to provide nice services such as [leaderboards](Ranking-Protocol).

### Password authentication
Your password is never sent to the authentication server. Instead, it is used to derive the kerberos key. The kerberos key can be used to decrypt the ticket from the [authentication service](Authentication-Protocol). This is a simple but effective authentication scheme: if you don't know the password you can't decrypt the ticket, and therefore you can not connect to the secure server.

The ticket can be retrieved with one of the following methods:
1. **[Login](Authentication-Protocol#1-login)**. This method takes a single parameter: the username. The response contains your user id, the location of the secure server, and a ticket that is encrypted with the kerberos key that belongs to the given user.
2. **[LoginEx](Authentication-Protocol#2-loginex)**. This method takes extra data in addition to the username, such as the server version that the client is expecting and a token that the client received along with its username and password. It is not necessary to request a token every time you want to log in, as you can simply use the **[Login](Authentication-Protocol#1-login)** method which does not require a token.
3. **[RequestTicket](Authentication-Protocol#3-requestticket)**. This method is a bit different. It requires that you know your user id in advance (for example, from the **[Login](Authentication-Protocol#1-login)** method) method. The **[RequestTicket](Authentication-Protocol#3-requestticket)** method explicitly takes a **source** and **target user** id and returns an appropriate ticket. It's possible that the **target user** of the ticket that is returned by the **[Login](Authentication-Protocol#1-login)** or **[LoginEx](Authentication-Protocol#2-loginex)** method does not belong to the secure server. In that case the **[RequestTicket](Authentication-Protocol#3-requestticket)** method can be used to get the correct ticket.

To figure out if it needs to request a new ticket with the **[RequestTicket](Authentication-Protocol#3-requestticket)** method, NEX compares the **target user** id in the decrypted ticket against the user id in connection info for the secure server.

### Authentication with token
On Switch servers, authentication works slightly differently. Special accounts, such as **guest**, still use password-based authentication, but normal users must provide an id token to log in. If an id token is not provided, or if it is invalid, the server refuses to hand out a ticket and returns an error code instead.

Because the **[Login](Authentication-Protocol#1-login)** method only takes a username, it is not possible to use this method to log in on a normal user account on Switch servers. It is also not possible use the **[RequestTicket](Authentication-Protocol#3-requestticket)** method for normal users on Switch servers. Instead, one of the following methods must be used, depending on the NEX version:

1. **[ValidateAndRequestTicketWithCustomData](Authentication-Protocol#2-loginex)** (before NEX 4.4.0). The id token is sent to the server in the AuthenticationInfo parameter. If the id token is valid, the kerberos key is sent to the client in the response, along with ticket.
2. **[ValidateAndRequestTicketWithParam](Authentication-Protocol#6-validateandrequestticketwithparam)** (NEX 4.4.0 and later). This method is the same as above, but with slightly different request and response parameters.

### Kerberos key derivation
If password-based authentication is used, the kerberos key is generated as follows:

**3DS / Wii U**: The password is MD5-hashed `65000 + pid % 1024` times.

**Switch**: The key is `MD5(MD5(password) + PACK("<Q", pid))`

Here, `pid` and `password` are the user id and password of the **source user**.

## Ticket Encryption
The ticket is encrypted with the kerberos key, which is either derived from the password and user id of the **source user** or received from the [authentication service](Authentication-Protocol). First, the ticket is encrypted with RC4. Then a HMAC-MD5 of the encrypted data is appended to the data. The decryption process is the reverse: first check the HMAC, then decrypt.

## Ticket Format
After decryption, the ticket contains the following data:

| Type | Description |
| --- | --- |
| Bytes | Session key |
| [PID] | Target user id |
| [Buffer] | [Internal ticket data](#internal-ticket-data) |

The length of the session key is always 32 bytes, except in communication with the 3DS / Wii U friends server, in which case it's 16 bytes.

### Internal ticket data
This part of the ticket is used to pass information from the authentication server to the secure server. It is encrypted in the same way as the ticket itself (RC4 + HMAC), but with the key that's derived from the **target user**. Because only the servers know the password of the account that belongs to the secure server, the client can not decrypt this part of the ticket.

The format of the internal ticket data was updated at some point. In the old format, the internal ticket data was encrypted directly with the key of the **target user**. In the new format, a random key is sent along with the internal ticket data in plain text, which is combined with the key of the **target user** to get the final key that the internal ticket data is encrypted with.

### Old version
| Type | Description |
| --- | --- |
| [Ticket Info](#ticket-info) | Encrypted ticket info |

### New version
| Type | Description |
| --- | --- |
| [Buffer] | Random key |
| [Buffer] | Encrypted ticket info |

The final encryption key is calculated as follows: `MD5(target_user_key + random_key)`

### Ticket Info
The date time is used to check ticket expiration. A ticket is valid for exactly 2 minutes.

| Type | Description |
| --- | --- |
| [DateTime] | Time at which the ticket was issued |
| [PID] | Source user id |
| Bytes | Session key |

[Buffer]: NEX-Common-Types#buffer
[PID]: NEX-Common-Types#pid
[DateTime]: NEX-Common-Types#datetime