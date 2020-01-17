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

### Protocol
All peer-to-peer packets are sent through UDP. The packet format is described [here](PIA-Protocol). Once a connection between consoles has been established they talk to each other through a bunch of [protocols / services](PIA-Protocols). Most of these are only used internally by PIA to set up and manage the connection. However, at some point, the game can start sending data packets to the other console. This usually happens through the [reliable](Reliable-Protocol) or [unreliable protocol](Unreliable-Protocol).

### Session management
A group of connected consoles is called a mesh. Every mesh has a single "host" that controls the mesh. Initially, the console that created the mesh is the host. Once the host leaves the mesh, a new host is selected through "host migration". The host performs important tasks such as processing join requests by newcomers. The host may also perform some game-specific tasks. For example, in Mario Kart 8, the host decides which track is chosen by the track roulette.

### Joining a mesh
The following steps are performed to join a mesh:

1. Your console finds a mesh through [matchmaking](#matchmaking).
2. Your console [establishes a connection](#connection-establishment) to the host of the mesh.
3. Your console sends a [join request](Mesh-Protocol) to the host.
4. The host decides if it wants to accept the join request. For example, if the mesh already has the maximum number of participants it may reject the join request.
5. The host sends a [join response](Mesh-Protocol) to your console to inform it about its decision. If the join request was accepted, the join response also contains the addresses of the other consoles in the mesh.
6. If the join request was accepted, your console establishes a connection to the other consoles in the mesh.
7. Finally, your console starts sending/receiving data packets to/from the other consoles.

### Connection establishment
After acquiring the [StationLocation](PIA-Types#stationlocation) of another console elsewhere (e.g. from [matchmaking](#matchmaking) or the [join response](#joining-a-mesh)), the following steps are performed to establish a connection with the console:

1. If necessary, [NAT traversal](#nat-traversal) is performed.
2. Your console sends a [connection request](Station-Protocol#connection-request) to the other console.
3. If the other console does not want to accept the request, it sends a denying [connection response](Station-Protocol#connection-response) to your console. Otherwise, it [acknowledges](Station-Protocol#ack) the request and sends an inverse connection request to your console.
4. If your console does not want to accept the inverse connection request for some reason, it sends a denying connection response to the other console. Otherwise, it acknowledges the request and sends a connection response to the other console.
5. The other console sends a connection response to your console.

### NAT traversal
If NEX is used for matchmaking it is often necessary to perform NAT traversal. This is not necessary in LDN and LAN mode, because the consoles are already on the same network in these modes.

The following steps are performed for NAT traversal:

1. Your console calls the [RequestProbeInitiation](NAT-Traversal-Protocol#1-requestprobeinitiation) or [RequestProbeInitiationExt](NAT-Traversal-Protocol#3-requestprobeinitiationext) method on the on the game server.
2. The server sends an [InitiateProbe](NAT-Traversal-Protocol#2-initiateprobe) request to the other console.
3. The other console sends a [probe request](NAT-Traversal-Protocol-(PIA)#probe-request) directly to your console. At the same time, it calls [RequestProbeInitiation](NAT-Traversal-Protocol#1-requestprobeinitiation) or [RequestProbeInitiationExt](NAT-Traversal-Protocol#3-requestprobeinitiationext) on the game server.
4. When your console receives the probe requests, it sends a [probe reply](NAT-Traversal-Protocol-(PIA)#probe-reply) directly to the other console. When the server receives the probe initation request, it sends an [InitiateProbe](NAT-Traversal-Protocol#2-initiateprobe) request to your console.
5. When your console receives the InitiateProbe request from the server it sends a probe request directly to the other console.
6. The other console answers your probe request with a probe response.
7. NAT traversal has been completed and the consoles can now [establish a connection](#establishing-a-connection) using the [station protocol](Station-Protocol).