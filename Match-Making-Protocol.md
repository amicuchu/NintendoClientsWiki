## [[NEX Protocols]] > Match Making (0x15)

| Method ID | Method Name |
| --- | --- |
| 1 | [RegisterGathering](#1-registergathering) |
| 2 | [UnregisterGathering](#2-unregistergathering) |
| 3 | [UnregisterGatherings](#3-unregistergatherings) |
| 4 | [UpdateGathering](#4-updategathering) |
| 5 | [Invite](#5-invite) |
| 6 | [AcceptInvitation](#6-acceptinvitation) |
| 7 | [DeclineInvitation](#7-declineinvitation) |
| 8 | [CancelInvitation](#8-cancelinvitation) |
| 9 | [GetInvitationsSent](#9-getinvitationssent) |
| 10 | [GetInvitationsReceived](#10-getinvitationsreceived) |
| 11 | [Participate](#11-participate) |
| 12 | [CancelParticipation](#12-cancelparticipation) |
| 13 | [GetParticipants](#13-getparticipants) |
| 14 | [AddParticipants](#14-addparticipants) |
| 15 | [GetDetailedParticipants](#15-getdetailedparticipants) |
| 16 | [GetParticipantsURLs](#16-getparticipantsurls) |
| 17 | [FindByType](#17-findbytype) |
| 18 | [FindByDescription](#18-findbydescription) |
| 19 | [FindByDescriptionRegex](#19-findbydescriptionregex) |
| 20 | [FindByID](#20-findbyid) |
| 21 | [FindBySingleID](#21-findbysingleid) |
| 22 | [FindByOwner](#22-findbyowner) |
| 23 | [FindByParticipants](#23-findbyparticipants) |
| 24 | [FindInvitations](#24-findinvitations) |
| 25 | [FindBySQLQuery](#25-findbysqlquery) |
| 26 | [LaunchSession](#26-launchsession) |
| 27 | [UpdateSessionURL](#27-updatesessionurl) |
| 28 | [GetSessionURL](#28-getsessionurl) |
| 29 | [GetState](#29-getstate) |
| 30 | [SetState](#30-setstate) |
| 31 | [ReportStats](#31-reportstats) |
| 32 | [GetStats](#32-getstats) |
| 33 | [DeleteGathering](#33-deletegathering) |
| 34 | [GetPendingDeletions](#34-getpendingdeletions) |
| 35 | [DeleteFromDeletions](#35-deletefromdeletions) |
| 36 | [MigrateGatheringOwnershipV1](#36-migrategatheringownershipv1) |
| 37 | [FindByDescriptionLike](#37-findbydescriptionlike) |
| 38 | [RegisterLocalURL](#38-registerlocalurl) |
| 39 | [RegisterLocalURLs](#39-registerlocalurls) |
| 40 | [UpdateSessionHostV1](#40-updatesessionhostv1) |
| 41 | [GetSessionURLs](#41-getsessionurls) |
| 42 | [UpdateSessionHost](#42-updatesessionhost) |
| 43 | [UpdateGatheringOwnership](#43-updategatheringownership) |
| 44 | [MigrateGatheringOwnership](#44-migrategatheringownership) |

# (1) RegisterGathering
## Request
| Type | Name | Description |
| --- | --- | --- |
| [Data]&lt;[Gathering]&gt; | anyGathering | Gathering |

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
| [Data]&lt;[Gathering]&gt; | anyGathering | Gathering |

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

# (6) AcceptInvitation
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |
| [String] | strMessage | Message |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result |

# (7) DeclineInvitation
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |
| [String] | strMessage | Message |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result |

# (8) CancelInvitation
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |
| [List]&lt;[PID]&gt; | lstPrincipals | User pids |
| [String] | strMessage | Message |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result |

# (9) GetInvitationsSent
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[Invitation]&gt; | lstInvitations | Invitations |

# (10) GetInvitationsReceived
## Request
This method does not take any parameters.

## Response
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[Invitation]&gt; | lstInvitations | Invitations |

# (11) Participate
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |
| [String] | strMessage | Message |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result | 

# (12) CancelParticipation
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |
| [String] | strMessage | Message |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result |

# (13) GetParticipants
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[PID]&gt; | lstParticipants | Participant pids |

# (14) AddParticipants
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |
| [List]&lt;[PID]&gt; | lstParticipants | Participant pids |
| [String] | strMessage | Message |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result | 

# (15) GetDetailedParticipants
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[ParticipantDetails]&gt; | lstParticipants | Participant details | 

# (16) GetParticipantsURLs
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[StationURL]&gt; | lstStationURL | Participant urls |

# (17) FindByType
## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strType | Type |
| [ResultRange] | resultRange | Result range |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[Data]&lt;[Gathering]&gt;&gt; | lstGathering | Gatherings |

# (18) FindByDescription
## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strDescription | Description |
| [ResultRange] | resultRange | ResultRange |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[Data]&lt;[Gathering]&gt;&gt; | lstGathering | Gatherings |

# (19) FindByDescriptionRegex
## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strDescriptionRegex | Description regex |
| [ResultRange] | resultRange | ResultRange |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[Data]&lt;[Gathering]&gt;&gt; | lstGathering | Gatherings |

# (20) FindByID
## Request
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;Uint32&gt; | lstID | Gathering ids |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[Data]&lt;[Gathering]&gt;&gt; | lstGathering | Gatherings |

# (21) FindBySingleID
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | id | Gathering id |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | bResult | Result | 
| [Data]&lt;[Gathering]&gt; | pGathering | Gathering |

# (22) FindByOwner
## Request
| Type | Name | Description |
| --- | --- | --- |
| [PID] | id | Owner pid |
| [ResultRange] | resultRange | ResultRange |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[Data]&lt;[Gathering]&gt;&gt; | lstGathering | Gatherings |

# (23) FindByParticipants
## Request
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[PID]&gt; | pid | Participant pids |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[Data]&lt;[Gathering]&gt;&gt; | lstGathering | Gatherings |

# (24) FindInvitations
## Request
| Type | Name | Description |
| --- | --- | --- |
| [ResultRange] | resultRange | Result range |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[Data]&lt;[Gathering]&gt;&gt; | lstGathering | Gatherings |

# (25) FindBySQLQuery
## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strQuery | SQL query |
| [ResultRange] | resultRange | Result range |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[Data]&lt;[Gathering]&gt;&gt; | lstGathering | Gatherings |

# (26) LaunchSession
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |
| [String] | strURL | Session url |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result | 

# (27) UpdateSessionURL
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |
| [String] | strURL | Session url |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result | 

# (28) GetSessionURL
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result | 
| [String] | strURL | Session url |

# (29) GetState
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result |
| Uint32 | uiState | State |

# (30) SetState
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |
| Uint32 | uiNewState | New state |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result | 

# (31) ReportStats
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |
| [List]&lt;[GatheringStats]&gt; | lstStats | Stats |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result | 

# (32) GetStats
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | idGathering | Gathering id |
| [List]&lt;Uint32&gt; | lstParticipants | Participant pids |
| [List]&lt;byte&gt; | lstColumns | Columns |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result |
| [List]&lt;[GatheringStats]&gt; | plstStats | Stats |

# (33) DeleteGathering
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | gid | Gathering id |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result | 

# (34) GetPendingDeletions
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | uiReason | Reason |
| [ResultRange] | resultRange | Result range |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result | 
| [List]&lt;[DeletionEntry]&gt; | lstDeletions | Deletions |

# (35) DeleteFromDeletions
## Request
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;Uint32&gt; | lstDeletions | Deletions |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result | 

# (36) MigrateGatheringOwnershipV1
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | gid | Gathering id |
| [List]&lt;[PID]&gt; | lstPotentialNewOwnersID | Potential new owner pids |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result | 

# (37) FindByDescriptionLike
## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strDescriptionLike | Description like |
| [ResultRange] | resultRange | Result range |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[Data]&lt;[Gathering]&gt;&gt; | lstGathering | Gatherings |

# (38) RegisterLocalURL
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | gid | Gathering id |
| [StationURL] | url | Url |

## Response
This method does not return anything.

# (39) RegisterLocalURLs
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | gid | Gathering id |
| [List]&lt;[StationURL]&gt; | lstUrls | Urls |

## Response
This method does not return anything.

# (40) UpdateSessionHostV1
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | gid | Gathering id |

## Response
This method does not return anything.

# (41) GetSessionURLs
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | gid | Gathering id |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[StationURL]&gt; | lstURLs | Session urls |

# (42) UpdateSessionHost
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | gid | Gathering id |
| Bool | isMigrateOwner | Migrate owner |

## Response
This method does not return anything.

# (43) UpdateGatheringOwnership
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | gid | Gathering id |
| Bool | participantsOnly | Participants only |

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result | 

# (44) MigrateGatheringOwnership
## Request
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | gid | Gathering id |
| [List]&lt;[PID]&gt; | lstPotentialNewOwnersID | Potential new owner pids |
| Bool | participantsOnly | Participants only |

## Response
This method does not return anything.

[String]: NEX-Common-Types#string
[StationURL]: NEX-Common-Types#station-url
[List]: NEX-Common-Types#list
[PID]: NEX-Common-Types#pid
[Data]: NEX-Common-Types#any-data-holder
[Structure]: NEX-Common-Types#structure
[ResultRange]: NEX-Common-Types#result-range-structure
[Gathering]: Match-Making-Types#gathering-structure
[GatheringStats]: Match-Making-Types#gathering-stats-structure
[ParticipantDetails]: Match-Making-Types#participant-details-structure
[Invitation]: Match-Making-Types#invitation-structure
[DeletionEntry]: Match-Making-Types#deletion-entry-structure