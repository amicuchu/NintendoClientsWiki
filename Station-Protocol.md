[[PIA Protocols]] > Station Protocol (0x100)
---

| Protocol Port | Description |
| --- | --- |
| 0 | Unreliable |
| 1 | Reliable |

| Message Type | Description |
| --- | --- |
| 1 | [Connection request](#connection-request) |
| 2 | [Connection response](#connection-response) |
| 3 | [Disconnection request](#disconnection-request) |
| 4 | [Disconenction response](#disconnection-response) |
| 5 | [Ack](#ack) |
| 6 | [Relay connection request](#relay-connection-request) |
| 7 | [Relay connection response](#relay-connection-response) |

# Connection request
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Message type |
| 0x1 | 1 | Connection id |
| 0x2 | 1 | Version |
| 0x3 | 1 | Is inverse connection request |
| 0x4 | 54 | [StationConnectionInfo] |
| 0x3A | 4 | Ack id |

# Connection response
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Message type |
| 0x1 | 1 | Result |
| 0x2 | 1 | Always 3? |
| 0x3 | 1 | Always 3? |

Only present if result is OK:

| Offset | Size | Description |
| --- | --- | --- |
| 0x4 | 66 | [IdentificationInfo] |
| 0x46 | 4 | Ack id |

### Connection result
| Value | Description |
| --- | --- |
| 0 | OK |
| 1 | Connection denied |
| 2 | Connection denied |

# Disconnection request
# Disconnection response
# Ack
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Message type |
| 0x1 | 3 | Padding |
| 0x4 | 4 | Ack id |

# Relay connection request
# Relay connection response

[StationConnectionInfo]: PIA-Types#stationconnectioninfo
[IdentificationInfo]: PIA-Types#identificationinfo