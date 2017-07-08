[[PIA Protocols]] > Mesh Protocol (0x200)
---

In Mario Kart 8, this protocol is actually called "SessionProtocol".   
Message id is part of the packet payload. The message id in the packet header is always 0 in this protocol.

| Message ID | Description |
| --- | --- |
| 0x01 | Join request |
| 0x02 | Join response |
| 0x04 | Leave request |
| 0x08 | Leave response |
| 0x10 | Destroy mesh |
| 0x11 | Destroy response |
| 0x20 | Update mesh |
| 0x21 | Kickout notice |
| 0x22 | Dummy message |
| 0x24 | Connection failure notice |
| 0x40 | Greeting |
| 0x41 | Migration finish |
| 0x42 | Greeting response |
| 0x44 | Migration start |
| 0x48 | Migration response |
| 0x49 | Multi migration start |
| 0x4A | Multi migration rank decision |
| 0x80 | Connection report |
| 0x81 | Relay route directions |