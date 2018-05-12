## [[NEX Protocols]] > Match Making (0x15)

| Method ID | Method Name |
| --- | --- |
| 1 | [RegisterGathering](#1-registergathering) |
| 2 | [UnregisterGathering](#2-unregistergathering) |
| 3 | [UnregisterGatherings](#3-unregistergatherings) |
| 4 | [UpdateGathering](#4-updategathering) |
| 5 | [Invite](#5-invite) |
| 6 | AcceptInvitation |
| 7 | DeclineInvitation |
| 8 | CancelInvitation |
| 9 | GetInvitationsSent |
| 10 | GetInvitationsReceived |
| 11 | Participate |
| 12 | CancelParticipation |
| 13 | GetParticipants |
| 14 | AddParticipants |
| 15 | GetDetailedParticipants |
| 16 | GetParticipantsURLs |
| 17 | FindByType |
| 18 | FindByDescription |
| 19 | FindByDescriptionRegex |
| 20 | FindByID |
| 21 | FindBySingleID |
| 22 | FindByOwner |
| 23 | FindByParticipants |
| 24 | FindInvitations |
| 25 | FindBySQLQuery |
| 26 | LaunchSession |
| 27 | UpdateSessionURL |
| 28 | GetSessionURL |
| 29 | GetState |
| 30 | SetState |
| 31 | ReportStats |
| 32 | GetStats |
| 33 | DeleteGathering |
| 34 | GetPendingDeletions |
| 35 | DeleteFromDeletions |
| 36 | MigrateGatheringOwnershipV1 |
| 37 | FindByDescriptionLike |
| 38 | RegisterLocalURL |
| 39 | RegisterLocalURLs |
| 40 | UpdateSessionHostV1 |
| 41 | GetSessionURLs |
| 42 | UpdateSessionHost |
| 43 | UpdateGatheringOwnership |
| 44 | MigrateGatheringOwnership |

# (1) RegisterGathering
## Request
| Type | Name | Description |
| --- | --- | --- |
| [Data]&lt;Gathering&gt; | anyGathering | Gathering |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | %retval% | Gathering id |

# (2) UnregisterGathering
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result |

# (3) UnregisterGatherings
## Request
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;Uint32&gt; | lstGatherings | Gathering ids |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result |

# (4) UpdateGathering
## Request
| Type | Name | Description |
| --- | --- | --- |
| [Data]&lt;Gathering&gt; | anyGathering | Gathering |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result |

# (5) Invite
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |
| [List]&lt;[PID]&gt; | lstPrincipals | Invited user pids |
| [String] | strMessage | Message |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result |

[String]: NEX-Common-Types#string
[List]: NEX-Common-Types#list
[PID]: NEX-Common-Types#pid
[Data]: NEX-Common-Types#any-data-holder