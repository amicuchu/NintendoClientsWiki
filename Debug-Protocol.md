[NEX Protocols](NEX-Protocols.md) > Debug (0x74)
---

This protocol seems to log your RMC requests.

| Method ID | Method Name |
| --- | --- |
| 1 | [EnableApiRecorder](#1-enableapirecorder) |
| 2 | [DisableApiRecorder](#2-disableapirecorder) |
| 3 | [IsApiRecorderEnabled](#3-isapirecorderenabled) |
| 4 | [GetApiCalls](#4-getapicalls) |
| 5 | SetExcludeJoinedMatchmakeSession |
| 6 | GetExcludeJoinedMatchmakeSession |
| 7 | GetApiCallSummary |

# (1) EnableApiRecorder
This method does not take any parameters and does not return anything.

# (2) DisableApiRecorder
This method does not take any parameters and does not return anything.

# (3) IsApiRecorderEnabled
## Request
This method does not take any parameters.

## Response
| Type | Description |
| --- | --- |
| Bool | True if the api recorder is enabled |

# (4) GetApiCalls
This method returns `RendezVous::InvalidConfiguration` if the api recorder is disabled.

## Request
| Type | Description |
| --- | --- |
| [List]&lt;[PID]&gt; | Pids |
| [DateTime] | Unknown |
| [DateTime] | Unknown |

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[ApiCall](#apicall-structure)&gt; | Api calls |

### ApiCall ([Structure])
| Type | Description |
| --- | --- |
| [String] | Method name |
| [DateTime] | Call time |
| [PID] | User id |

[Result]: NEX-Common-Types.md#result
[String]: NEX-Common-Types.md#string
[Buffer]: NEX-Common-Types.md#buffer
[qBuffer]: NEX-Common-Types.md#qbuffer
[List]: NEX-Common-Types.md#list
[Map]: NEX-Common-Types.md#map
[DateTime]: NEX-Common-Types.md#datetime
[Structure]: NEX-Common-Types.md#structure
[Data]: NEX-Common-Types.md#anydataholder
[PID]: NEX-Common-Types.md#pid
[ResultRange]: NEX-Common-Types.md#resultrange-structure