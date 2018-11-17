## General
Nintendo offers a networking library called PIA, which provides a framework to set up and maintain peer-to-peer connections.

## Match making
PIA supports three different network types.

**NEX:** Match making is done by game servers (with [NEX](NEX-Overview-(Game-Servers))). This mode often requires NAT traversal.

**LDN:** PIA uses [nn::ldn](https://switchbrew.org/wiki/LDN_services) to find and connect to other consoles. This mode is only available on Nintendo Switch.

**LAN:** PIA uses UDP broadcast packets to find other consoles (see [[Local LAN Play]]). This mode is only available on Nintendo Switch.

## Protocol
The packet format has been described here: [[PIA Protocol]]