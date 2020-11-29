[PIA Protocols](PIA-Protocols.md) > RTT Protocol
---

All messages are sent through port 1 and contain the following payload:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | 0 = request, 1 = response |
| 0x4 | 4 | Padding (always 0) |
| 0x8 | 8 | System time (OSGetSystemTime on Wii U, nn::os::GetSystemTick on Switch) |

