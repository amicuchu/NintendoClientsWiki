PIA is Nintendo's networking library that provides a framework to set up and maintain peer-to-peer connections.

### Match making
PIA supports three different network types.

<table>
  <tr>
    <td><b>NEX</b></td><td>Match making is done by game servers (with <a href="NEX-Overview-(Game-Servers)">NEX</a>). This mode often requires NAT traversal.</td>
  </tr>
  <tr>
    <td><b>LDN</b></td><td>This is the default mode for local multiplayer. PIA uses <a href="https://switchbrew.org/wiki/LDN_services">nn::ldn</a> to find and connect to other consoles. This mode is only available on Nintendo Switch.</td>
  </tr>
  <tr>
    <td><b>LAN</b></td><td>This is an alternative mode for local multiplayer. It can usually be enabled by pressing L + R + Left Stick in one of the menus. In this mode, PIA uses UDP broadcast packets to find other consoles (see [[LAN Protocol]]). This mode is only available on Nintendo Switch.
  </tr>
</table>

### Session management
A group of connected consoles is called a mesh. Every mesh has a single "host" that controls the mesh. Depending on the game, the host may also perform some special tasks. For example, in Mario Kart 8, the host decides which track is chosen by the track roulette. Initially, the console that created the mesh is the host. Once the host leaves the mesh, a new host is selected through "host migration".

The packet format has been described here: [[PIA Protocol]]