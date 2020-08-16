This server is used to detect NAT properties of the router in order to perform NAT traversal.

This server is at:
* nncs1-lp1.n.n.srv.nintendo.net (primary server)
* nncs2-lp1.n.n.srv.nintendo.net (secondary server)

The protocol consists of simple UDP messages through port 10025 (primary port) or 10125 (secondary port). Messages are encoded in big endian byte order.

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Message type |
| 0x4 | 4 | Port number as perceived by server |
| 0x8 | 4 | IP address as perceived by server |
| 0xC | 4 | Unknown |
