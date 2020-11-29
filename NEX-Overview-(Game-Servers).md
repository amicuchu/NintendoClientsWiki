NEX is Nintendo's networking library that provides a client for game servers. Almost all 3DS, Wii U and Switch games with online features use NEX.

Nintendo hasn't written it from scratch. It's based on [Quazal Rendez-Vous](http://web.archive.org/web/20180823162719/http://quazal.com/rendez-vous.htm), so some things like the [PRUDP Protocol](PRUDP-Protocol.md) may be seen in other games that use Quazal.

### Finding the game servers
To connect to a game server, you first need to find it. Every platform has its own way to find a game server. A list of game server ids can be found here: [Game Server List](Game-Server-List.md).

<table>
  <tr>
    <td><b>3DS</b></td><td>The game server location is requested from the NASC server</td>
  </tr>
  <tr>
    <td><b>Wii U</b></td><td>The game server location is requested from the [account server](account-server.md) (/provider/nex_token/@me)</td>
  </tr>
  <tr>
    <td><b>Switch</b></td><td>The game server is found by DNS lookup: g<code>&lt;game server id&gt;</code>-lp1.s.n.srv.nintendo.net</td>
  </tr>
</table>

This is the location of the authentication server.

### The protocols used by NEX
![](https://www.dropbox.com/s/wahcq2ifyncd3bu/protocols.png?raw=1)

At the highest level, NEX provides a bunch of [services](NEX-Protocols.md), with each service providing several methods. To achieve this, NEX uses a simple [RMC protocol](RMC-Protocol.md) (remote method call). Whenever a game wants to call a method on a service, NEX builds an RMC request and sends it through the underlying connection.

The underlying protocol varies per game and platform. Originally, the purpose of [PRUDP](PRUDP-Protocol.md) was to reliably send UDP packets. Starting with Nintendo Switch, NEX also supports TCP and WebSocket as underlying protocol however.

<table>
  <tr>
    <td><b>3DS</b></td><td>Packets are encoded using <a href="PRUDP-Protocol#v0-format">PRUDP V0</a> or <a href="PRUDP-Protocol#v1-format">PRUDP V1</a></td>
  </tr>
  <tr>
    <td><b>Wii U</b></td><td>Packets are normally encoded using <a href="PRUDP-Protocol#v1-format">PRUDP V1</a>. Only one server still uses <a href="PRUDP-Protocol#v0-format">PRUDP V0</a>: the friends server.</td>
  </tr>
  <tr>
    <td><b>Switch</b></td><td>Switch games use <a href="PRUDP-Protocol#lite-format">PRUDP Lite</a> on top of WebSockets.</td>
  </tr>
</table>

### Authentication
Every game server actually consists of two servers: an authentication server and a secure server. After retrieving login information elsewhere, NEX connects to the authentication server. This server only provides a single service: the [authentication service](Authentication-Protocol.md).

With UDP as underlying protocol, the connection to the authentication server isn't secure. Anyone with enough knowledge can decrypt the packets, but that's not a problem: the only purpose of the authentication server is to authenticate the user and set up a secure connection to the secure server.

For more details on authentication and the steps that are required to connect to the secure server, read the page about [kerberos authentication](Kerberos-Authentication.md).