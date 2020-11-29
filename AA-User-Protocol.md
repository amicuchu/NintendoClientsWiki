## [NEX Protocols](NEX-Protocols.md) > AA User (0x7B)

| Method ID | Method Name |
| --- | --- |
| 1 | [RegisterApplication](#1-registerapplication) |
| 2 | [UnregisterApplication](#2-unregisterapplication) |
| 3 | [SetApplicationInfo](#3-setapplicationinfo) |
| 4 | [GetApplicationInfo](#4-getapplicationinfo) |

# (1) RegisterApplication
## Request
| Type | Description |
| --- | --- |
| Uint64 | Title id |

## Response
This method does not return anything.

# (2) UnregisterApplication
## Request
| Type | Description |
| --- | --- |
| Uint64 | Title id |

## Response
This method does not return anything.

# (3) SetApplicationInfo
## Request
| Type | Description |
| --- | --- |
| [List]&lt;[ApplicationInfo](#applicationinfo)&gt; | Application info |

## Response
This method does not return anything.

# (4) GetApplicationInfo
## Request
This method does not take any parameters.

## Response
| Type | Description |
| --- | --- |
| [List]&lt;[ApplicationInfo](#applicationinfo-structure)&gt; | Application info |

# Types
## ApplicationInfo ([Structure])
| Type | Description |
| --- | --- |
| Uint64 | Title id |
| Uint16 | Title version |

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