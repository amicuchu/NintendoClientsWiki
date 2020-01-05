This page lists all protocols that are part of the [[PIA protocol]].

At some point, Nintendo changed the protocol ids. All Switch games that use PIA version 5.9 or newer use the new protocol ids. All Wii U games and older Switch games use the old protocol ids.

Also, the clone protocol used to be single protocol, but was split into several protocols around PIA version 5.14. Before the split, the id of the clone protocol was 0x74. After the split, the id of the main clone protocol became 0x73, and 0x74 was assigned to the atomic clone protocol.

| Old | New | Protocol |
| --- | --- | --- |
| 0x0080 |      | Relay Protocol |
| 0x00C0 |      | Keep Alive Protocol |
| 0x0100 | 0x14 | [[Station Protocol]] |
| 0x0200 | 0x18 | [[Mesh Protocol]] |
| 0x0210 | 0x1C | Sync Clock Protocol |
| 0x0300 | 0x24 | LDN Protocol |
| 0x0400 | 0x34 | [NAT Traversal Protocol](NAT-Traversal-Protocol-(PIA)) |
| 0x0410 |      | Gateway Protocol |
| 0x0500 | 0x54 | Bandwidth Checker Protocol |
| 0x0600 | 0x58 | [[RTT Protocol]] |
| 0x1800 |      | Sync Protocol (old) |
| 0x1810 |      | Sync Protocol |
| 0x2000 | 0x68 | [[Unreliable Protocol]] |
| 0x2100 |      | Round Robin Unreliable Protocol |
| 0x2400 | 0x73 / 0x74 | Clone Protocol |
| | 0x74 | Clone Protocol (atomic) |
| | 0x76 | Clone Protocol (event) |
| | 0x77 | Clone Protocol (clock) |
| 0x2800 | 0x78 | Voice Protocol |
| 0x3000 | 0x7C | Reliable Protocol |
| 0x4400 | 0x44 | LAN Protocol |
| 0x7000 | 0x84 | Reliable Broadcast Protocol |
| 0x7200 | 0x94 | [[Session Protocol]] |
| 0x8000 | 0xA4 | Monitoring Data Protocol |
| 0x8200 |      | Relay Service Protocol |