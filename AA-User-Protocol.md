## [[NEX Protocols]] > AA User (0x7B)

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
| Uint16 | Unknown |

[Result]: NEX-Common-Types#result
[String]: NEX-Common-Types#string
[Buffer]: NEX-Common-Types#buffer
[qBuffer]: NEX-Common-Types#qbuffer
[List]: NEX-Common-Types#list
[Map]: NEX-Common-Types#map
[DateTime]: NEX-Common-Types#datetime
[Structure]: NEX-Common-Types#structure
[Data]: NEX-Common-Types#anydataholder
[PID]: NEX-Common-Types#pid
[ResultRange]: NEX-Common-Types#resultrange-structure