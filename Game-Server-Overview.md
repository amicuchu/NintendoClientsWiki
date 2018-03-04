## General
Nintendo offers a networking library called NEX. This library does everything that's needed to connect and talk to game servers. It's not actually written by Nintendo itself. Rather, it's a version of [Quazal Rendez-Vous](http://www.quazal.com/rendez-vous.htm) written specifically for Nintendo. Thus, some things like the [[PRUDP Protocol]] may be seen in other games that use Quazal.

NEX was first used on 3DS, later on Wii U, and now it's being used on Switch. While the underlying library is the same, it has received various (big) updates throughout its lifetime.

### The protocols used by NEX
At the lowest level, NEX uses a transport protocol called PRUDP. The main purpose of this protocol is to reliably send UDP packets, but it also offers encryption and compression algorithms. Nintendo doesn't use compression however.

At the highest level, NEX provides a bunch of [services](NEX-Protocols), with each service providing several methods that can be called. For example, to upload a score to a leaderboard, a game calls the [UploadScore](Ranking-Protocol#1-uploadscore) method of the [Ranking](Ranking-Protocol) service. To achieve this, NEX uses a simple [remote-method-call protocol](RMC-Protocol). Whenever a game wants to call a method on a service, NEX builds a RMC request and sends it through the PRUDP connection.

### Authentication
Each game server actually consists of two servers: an authentication server and a secure server. After retrieving login information elsewhere, NEX connects to the authentication server. This server only provides a single service: the [authentication service](Authentication-Protocol). The connection to the authentication server isn't secure. Anyone with enough knowledge can decrypt the packets, but don't be scared: the only purpose of the authentication server is to set up a secure connection to the secure server.

### Game server identification
Each game server has a unique game server id and a sandbox access key. The game server id is used to determine the location of the game server, either by DNS lookup (Switch) or from an external server (3DS/Wii U). The access key is used to calculate the PRUDP packet checksum. It's known by both the client and the server, but never sent throught the connection.

## 3DS
Login information is requested from the NASC server. Packets are encoded using [PRUDP V0](PRUDP-Protocol#v0-format).

## Wii U
Login information is requested from the [[Account Server]] (see /provider/nex_token/@me). Packets are normally encoded using [PRUDP V1](PRUDP-Protocol#v1-format). Only one server still uses [PRUDP V0](PRUDP-Protocol#v0-format): the friends server.

## Switch
The location of the game servers is found by DNS lookup: gXXXXXXXX-lp1.s.n.srv.nintendo.net where XXXXXXXX is the game server id. Furthermore, NEX now supports UDP, TCP and WebSockets as underlying protocol. Switch games are configured to use WebSockets. Since TCP and WebSockets are already reliability themselves, a new packet encoding is used, named PRUDP Lite.