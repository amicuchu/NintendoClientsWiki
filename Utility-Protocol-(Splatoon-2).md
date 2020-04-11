## [[NEX Protocols]] > [Utility (0x6E)](Utility-Protocol) > Splatoon 2

This page describes the methods that are only seen in Splatoon 2.

| Method ID | Method Name |
| --- | --- |
| 9 | [AcquireTagId](#9-acquiretagid) |
| 10 | [UpdateCurrentUser](#10-updatecurrentuser) |

# (9) AcquireTagId
## Request
| Type | Name |
| --- | --- |
| [List](NEX-Common-Types#list)&lt;Uint64&gt; | nexUniqueIds |

## Response
| Type | Name |
| --- | --- |
| Uint64 | pTagId |

# (10) UpdateCurrentUser
## Request
| Type | Name |
| --- | --- |
| [UpdateCurrentUserParam](#updatecurrentuserparam-structure) | param |

## Response
This method does not return anything.

## UpdateCurrentUserParam ([Structure](NEX-Common-Types#structure))
| Type | Name |
| --- | --- |
| [UniqueIdInfo](Utility-Protocol#uniqueidinfo-structure) | info |
| Uint8 | region |