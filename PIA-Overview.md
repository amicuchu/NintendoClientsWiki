PIA is Nintendo's networking library that provides a framework to set up and maintain peer-to-peer connections.

### Matchmaking
PIA supports three different network types.

<table>
  <tr>
    <td><b>NEX</b></td><td>Matchmaking is done by game servers (with <a href="NEX-Overview-(Game-Servers)">NEX</a>). This mode often requires NAT traversal.</td>
  </tr>
  <tr>
    <td><b>LDN</b></td><td>This is the default mode for local multiplayer. PIA uses <a href="https://switchbrew.org/wiki/LDN_services">nn::ldn</a> to find and connect to other consoles. This mode is only available on Nintendo Switch.</td>
  </tr>
  <tr>
    <td><b>LAN</b></td><td>This is an alternative mode for local multiplayer. It can usually be enabled by pressing L + R + Left Stick in one of the menus. In this mode, PIA uses UDP broadcast packets to find other consoles (see [[LAN Protocol]]). This mode is only available on Nintendo Switch.
  </tr>
</table>

### Session management
A group of connected consoles is called a mesh. Every mesh has a single "host" that controls the mesh. Initially, the console that created the mesh is the host. Once the host leaves the mesh, a new host is selected through "host migration". The host performs important tasks such as processing join requests by newcomers. The host may also perform some game-specific tasks. For example, in Mario Kart 8, the host decides which track is chosen by the track roulette.

### Joining a mesh
The following steps are performed to join a mesh:

1. Your console finds a mesh through [matchmaking](#matchmaking).
2. Your console [establishes a connection](#connection-establishment) to the host of the mesh.
3. Your console sends a [join request](Mesh-Protocol#join-request) to the host.
4. The host decides if it wants to accept the join request. If the mesh already has the maximum number of participants it may reject the join request for example.
5. The host sends a [join response](Mesh-Protocol#join-response) to your console to inform it about its decision. If the join request was accepted, the join response also contains the addresses of the other consoles in the mesh.
6. If the join request was accepted, your console establishes a connection to the other consoles in the mesh.
7. Finally, your console starts sending/receiving data packets to/from the other consoles.

### Connection establishment
The packet format has been described here: [[PIA Protocol]]