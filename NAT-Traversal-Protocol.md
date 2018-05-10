[[NEX Protocols]] > NAT Traversal (0x03)
---

| Method ID | Method Name |
| --- | --- |
| 1 | RequestProbeInitiation |
| 2 | InitiateProbe |
| 3 | RequestProbeInitiationExt |
| 4 | ReportNATTraversalResult |
| 5 | ReportNATProperties |
| 6 | GetRelaySignatureKey |
| 7 | ReportNATTraversalResultDetail |

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
| Type | Name |
| --- | --- |
| Uint32 | cid |
| Bool | result |
| Uint32 | rtt |

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


[List]: NEX-Common-Types#list
[StationURL]: NEX-Common-Types#stationurl
[DateTime]: NEX-Common-Types#datetime