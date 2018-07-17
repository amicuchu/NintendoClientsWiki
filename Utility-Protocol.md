## [[NEX Protocols]] > Utility (0x6E)

| Method ID | Method Name |
| --- | --- |
| 1 | [AcquireNexUniqueId](#1-acquirenexuniqueid) |
| 2 | [AcquireNexUniqueIdWithPassword](#2-acquirenexuniqueidwithpassword) |
| 3 | [AssociateNexUniqueIdWithMyPrincipalId](#3-associatenexuniqueidwithmyprincipalid) |
| 4 | [AssociateNexUniqueIdsWithMyPrincipalId](#4-associatenexuniqueidswithmyprincipalid) |
| 5 | [GetAssociatedNexUniqueIdWithMyPrincipalId](#5-getassociatednexuniqueidwithmyprincipalid) |
| 6 | [GetAssociatedNexUniqueIdsWithMyPrincipalId](#6-getassociatednexuniqueidswithmyprincipalid) |
| 7 | [GetIntegerSettings](#7-getintegersettings) |
| 8 | [GetStringSettings](#8-getstringsettings) |

# (1) AcquireNexUniqueId
## Request
This method does not take any parameters.

## Response
| Type | Name |
| --- | --- |
| Uint64 | pNexUniqueId |

# (2) AcquireNexUniqueIdWithPassword
## Request
This method does not take any parameters.

## Response
| Type | Name |
| --- | --- |
| [UniqueIdInfo] | pNexUniqueIdInfo |

# (3) AssociateNexUniqueIdWithMyPrincipalId
## Request
| Type | Name |
| --- | --- |
| [UniqueIdInfo] | uniqueIdInfo |

## Response
This method does not return anything.

# (4) AssociateNexUniqueIdsWithMyPrincipalId
## Request
| Type | Name |
| --- | --- |
| [List]&lt;[UniqueIdInfo]&gt; | uniqueIdInfo |

## Response
This method does not return anything.

# (5) GetAssociatedNexUniqueIdWithMyPrincipalId
## Request
This method does not take any parameters.

## Response
| Type | Name |
| --- | --- |
| [UniqueIdInfo] | pUniqueIdInfo |

# (6) GetAssociatedNexUniqueIdsWithMyPrincipalId
## Request
This method does not take any parameters.

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[UniqueIdInfo]&gt; | pUniqueIdInfo |

# (7) GetIntegerSettings
## Request
| Type | Name |
| --- | --- |
| Uint32 | integerSettingIndex |

## Response
| Type | Name |
| --- | --- |
| [Map]&lt;Uint16, Sint32&gt; | integerSettings |

# (8) GetStringSettings
## Request
| Type | Name |
| --- | --- |
| Uint32 | stringSettingIndex |

## Response
| Type | Name |
| --- | --- |
| [Map]&lt;Uint16, [String]&gt; | stringSettings |

# Types
## UniqueIdInfo ([Structure])
| Type | Name |
| --- | --- |
| Uint64 | nexUniqueId |
| Uint64 | nexUniqueIdPassword |

[String]: NEX-Common-Types#string
[Buffer]: NEX-Common-Types#buffer
[List]: NEX-Common-Types#list
[Map]: NEX-Common-Types#map
[Structure]: NEX-Common-Types#structure
[Data]: NEX-Common-Types#any-data-holder

[UniqueIdInfo]: uniqueidinfo-structure