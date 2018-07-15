## [[NEX Protocols]] > Match Making Ext (0x32)

| Method ID | Method Name |
| --- | --- |
| 1 | [EndParticipation](#1-endparticipation) |
| 2 | [GetParticipants](#2-getparticipants) |
| 3 | [GetDetailedParticipants](#3-getdetailedparticipants) |
| 4 | [GetParticipantsURLs](#4-getparticipantsurls) |
| 5 | [GetGatheringRelations](#5-getgatheringrelations) |
| 6 | [DeleteFromDeletions](#6-deletefromdeletions) |

# (1) EndParticipation
## Request
| Type | Name |
| --- | --- |
| Uint32 | idGathering |
| [String] | strMessage |

## Response
| Type | Name |
| --- | --- |
| Bool | %retval% |

# (2) GetParticipants
## Request
| Type | Name |
| --- | --- |
| Uint32 | idGathering |
| Bool | bOnlyActive |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[PID]&gt; | lstParticipants |

# (3) GetDetailedParticipants
## Request
| Type | Name |
| --- | --- |
| Uint32 | idGathering |
| Bool | bOnlyActive

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[ParticipantDetails]&gt; | lstParticipants |

# (4) GetParticipantsURLs
## Request
| Type | Name |
| --- | --- |
| [List]&lt;Uint32&gt; | lstGatherings |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[GatheringURL]&gt; | lstGatheringURLs |

# (5) GetGatheringRelations
## Request
| Type | Name |
| --- | --- |
| Uint32 | id |
| [String] | descr |

## Response
| Type | Name |
| --- | --- |
| [String] | %retval% |

# (6) DeleteFromDeletions
## Request
| Type | Name |
| --- | --- |
| [List]&lt;Uint32&gt; | lstDeletions |
| [PID] | pid |

## Response
This method does not return anything.

[List]: NEX-Common-Types#list
[PID]: NEX-Common-Types#pid
[String]: NEX-Common-Types#string
[Structure]: NEX-Common-Types#structure
[ParticipantDetails]: Match-Making-Types#participant-details-structure
[GatheringURL]: Match-Making-Types#gatheringurl-structure