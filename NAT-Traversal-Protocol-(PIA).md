[PIA Protocols](PIA-Protocols.md) > NAT Traversal
---

| Protocol Port | Description |
| --- | --- |
| 1 | [Probe request](#probe-request) |
| 2 | [Probe reply](#probe-reply) |
| 3 | [Dummy packet](#dummy-packet) |

# Probe request
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 16 | [NatProbeData](#natprobedata) |

# Probe reply
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 16 | [NatProbeData](#natprobedata) |

# Dummy packet
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 5 | "Dummy" |

# NatProbeData
| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Connection id (from [SecureConnection.Register](Secure-Protocol#1-register)) |
| 0x4 | 1 | Probe type (0=request 1=response) |
| 0x5 | 3 | Padding |
| 0x8 | 8 | System time (OSGetSystemTime on Wii U, nn::os::GetSystemTick on Switch) |