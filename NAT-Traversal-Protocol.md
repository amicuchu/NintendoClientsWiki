[[NEX Protocols]] > NAT Traversal (0x03)
---

| Method ID | Method Name |
| --- | --- |
| 1 | [RequestProbeInitiation](#1-requestprobeinitiation) |
| 2 | [InitiateProbe](#2-initiateprobe) |
| 3 | [RequestProbeInitiationExt](#3-requestprobeinitiationext) |
| 4 | [ReportNATTraversalResult](#4-reportnattraversalresult) |
| 5 | [ReportNATProperties](#5-reportnatproperties) |
| 6 | [GetRelaySignatureKey](#6-getrelaysignaturekey) |
| 7 | [ReportNATTraversalResultDetail](#7-reportnattraversalresultdetail) |

# (1) RequestProbeInitiation
## Request
| Type | Name |
| --- | --- |
| [List]&lt;[StationURL]&gt; | urlTargetList |

## Response
This method does not return anything.

# (2) InitiateProbe
## Request
| Type | Name |
| --- | --- |
| [StationURL] | urlStationToProbe |

## Response
This method does not return anything.

# (3) RequestProbeInitiationExt
## Request
| Type | Name |
| --- | --- |
| [List]&lt;[StationURL]&gt; | urlTargetList  |
| [StationURL] | urlStationToProbe |

## Response
This method does not return anything.

# (4) ReportNATTraversalResult
## Request
| Type | Name | Only present on |
| --- | --- | --- |
| Uint32 | cid | |
| Bool | result | |
| Uint32 | rtt | Wii U and Switch |

## Response
This method does not return anything.

# (5) ReportNATProperties
## Request
| Type | Name |
| --- | --- |
| Uint32 | natmapping |
| Uint32 | natfiltering |
| Uint32 | rtt |

## Response
This method does not return anything.

# (6) GetRelaySignatureKey
## Request
This method does not take any parameters.

## Response
| Type | Name |
| --- | --- |
| Int32 | relayMode |
| [DateTime] | currentUTCTime |
| [String] | address |
| Uint16 | port |
| Int32 | relayAddressType |
| Uint32 | gameServerID |

# (7) ReportNATTraversalResultDetail
## Request
| Type | Name |
| --- | --- |
| Uint32 | cid |
| Bool | result |
| Int32 | detail |
| Uint32 | rtt |

## Response
This method does not return anything.

[String]: NEX-Common-Types#string
[List]: NEX-Common-Types#list
[StationURL]: NEX-Common-Types#station-url
[DateTime]: NEX-Common-Types#date-time