[[NEX Protocols]] > Match Making Types
---

Since the match making methods are split across several protocols, this page documents all match making related structures in one place.

## Gathering ([Structure])
| Type | Name | Description |
| --- | --- | --- |
| Uint32 | m_idMyself | Gathering id |
| [PID] | m_pidOwner | Owner pid |
| [PID] | m_pidHost | Host pid |
| Uint16 | m_uiMinParticipants | Minimum number of participants |
| Uint16 | m_uiMaxParticipants | Maximum number of participants |
| Uint32 | m_uiParticipationPolicy | Participation policy |
| Uint32 | m_uiPolicyArgument | Policy argument |
| Uint32 | m_uiFlags | Flags |
| Uint32 | m_uiState | State |
| [String] | m_strDescription | Description |

## PersistentGathering ([Structure])
| This structure inherits from [Gathering](#gathering-structure) |
| --- |

| Type | Name |
| --- | --- |
| Uint32 | m_CommunityType |
| [String] | m_Password |
| [List]&lt;Uint32&gt; | m_Attribs |
| [Buffer] | m_ApplicationBuffer |
| [DateTime] | m_ParticipationStartDate |
| [DateTime] | m_ParticipationEndDate |
| Uint32 | m_MatchmakeSessionCount |
| Uint32 | m_ParticipationCount |

## MatchmakeSession ([Structure])
| This structure inherits from [Gathering](#gathering-structure) |
| --- |

| Type | Name | Only present on |
| --- | --- | --- |
| Uint32 | m_GameMode | |
| [List]&lt;Uint32&gt; | m_Attribs | |
| Bool | m_OpenParticipation | |
| Uint32 | m_MatchmakeSystemType | |
| [Buffer] | m_ApplicationBuffer | |
| Uint32 | m_ParticipationCount | |
| Uint8 | m_ProgressScore | NEX v3.5.0 and later |
| [Buffer] | m_SessionKey | NEX v3.0.0 and later |
| Uint32 | m_Option0 | NEX v3.5.0 and later |
| [MatchmakeParam](#matchmakeparam-structure) | m_MatchmakeParam | NEX v4.0.0 and later |
| [DateTime] | m_StartedTime | NEX v4.0.0 and later |
| [String] | m_UserPassword | NEX v4.0.0 and later |
| Uint32 | m_ReferGid | NEX v4.0.0 and later |
| Bool | m_UserPasswordEnabled | NEX v4.0.0 and later |
| Bool | m_SystemPasswordEnabled | NEX v4.0.0 and later |
| [String] | m_Codeword | NEX v4.0.0 and later |

## MatchmakeSessionSearchCriteria ([Structure])
| Type | Name | Only present on |
| --- | --- | --- |
| [List]&lt;[String]&gt; | m_Attribs | |
| [String] | m_GameMode | |
| [String] | m_MinParticipants | |
| [String] | m_MaxParticipants | |
| [String] | m_MatchmakeSystemType | |
| Bool | m_VacantOnly | |
| Bool | m_ExcludeLocked | |
| Bool | m_ExcludeNonHostPid | |
| Uint32 | m_SelectionMethod | |
| Uint16 | m_VacantParticipants | NEX v3.5.0 and later |
| [MatchmakeParam](#matchmakeparam-structure) | m_MatchmakeParam | NEX v4.0.0 and later |
| Bool | m_ExcludeUserPasswordSet | NEX v4.0.0 and later |
| Bool | m_ExcludeSystemPasswordSet | NEX v4.0.0 and later |
| Uint32 | m_ReferGid | NEX v4.0.0 and later |
| [String] | m_Codeword | NEX v4.0.0 and later |
| [ResultRange] | m_ResultRange | NEX v4.0.0 and later |

## CreateMatchmakeSessionParam ([Structure])
| Type | Name |
| --- | --- |
| [MatchmakeSession] | sourceMatchmakeSession |
| [List]&lt;[PID]&gt; | additionalParticipants |
| Uint32 | gidForParticipationCheck |
| Uint32 | createMatchmakeSessionOption |
| [String] | joinMessage |
| Uint16 | participationCount |

## JoinMatchmakeSessionParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | gid |
| [List]&lt;[PID]&gt; | additionalParticipants |
| Uint32 | gidForParticipationCheck |
| Uint32 | joinMatchmakeSessionOption |
| Uint8 | joinMatchmakeSessionBehavior |
| [String] | strUserPassword |
| [String] | strSystemPassword |
| [String] | joinMessage |
| Uint16 | participationCount |
| Uint16 | extraParticipants |
| [MatchmakeBlockListParam](#matchmakeblocklistparam-structure) | blockListParam |

## UpdateMatchmakeSessionParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | gid |
| Uint32 | modificationFlag |
| [List]&lt;Uint32&gt; | attributes |
| Bool | openParticipation |
| [Buffer] | applicationBuffer |
| Uint8 | progressScore |
| [MatchmakeParam](#matchmakeparam-structure) | matchmakeParam |
| [DateTime] | startedTime |
| [String] | userPassword |
| Uint32 | gameMode |
| [String] | description |
| Uint16 | minParticipants |
| Uint16 | maxParticipants |
| Uint32 | matchmakeSystemType |
| Uint32 | participationPolicy |
| Uint32 | policyArgument |
| [String] | codeword |

## MatchmakeBlockListParam ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | optionFlag |

## MatchmakeParam ([Structure])
| Type | Name |
| --- | --- |
| [Map]&lt;[String], [Variant]&gt; | m_Params |

## AutoMatchmakeParam ([Structure])
| Type | Name |
| --- | --- |
| [MatchmakeSession] | sourceMatchmakeSession |
| [List]&lt;[PID]&gt; | additionalParticipants |
| Uint32 | gidForParticipationCheck |
| Uint32 | autoMatchmakeOption |
| [String] | joinMessage |
| Uint16 | participationCount |
| [List]&lt;[MatchmakeSessionSearchCriteria](#matchmakesessionsearchcriteria-structure)&gt; | lstSearchCriteria |
| [List]&lt;Uint32&gt; | targetGids |
| [MatchmakeBlockListParam](#matchmakeblocklistparam-structure) | blockListParam |

## FindMatchmakeSessionByParticipantParam
| Type | Name |
| --- | --- |
| [List]&lt;[PID]&gt; | m_principalIdList |
| Uint32 | m_resultOptions |
| [MatchmakeBlockListparam](#matchmakeblocklistparam-structure) | m_blockListParam |

## FindMatchmakeSessionByParticipantResult
| Type | Name |
| --- | --- |
| [PID] | m_principalId |
| [MatchmakeSession](#matchmakesession-structure) | m_session |

## GatheringURLs ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | m_gid |
| [List]&lt;[StationURL]&gt; | m_lstStationURLs |

## Gathering Stats ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | m_pidParticipant |
| Uint32 | m_uiFlags |
| [List]&lt;Float&gt; | m_lstValues |

## Invitation ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | m_idGathering |
| Uint32 | m_idGuest |
| [String] | m_strMessage |

## Participant Details ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | m_idParticipant |
| [String] | m_strName |
| [String] | m_strMessage |
| Uint16 | m_uiParticipants |

## Deletion Entry ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | m_idGathering |
| [PID] | m_pid |
| Uint32 | m_uiReason |

## PlayingSession ([Structure])
| Type | Name |
| --- | --- |
| [PID] | m_PrincipalId |
| [Data]&lt;[Gathering]&gt; | m_Gathering |

## SimplePlayingSession ([Structure])
| Type | Name |
| --- | --- |
| [PID] | m_PrincipalID |
| Uint32 | m_GatheringID |
| Uint32 | m_GameMode |
| Uint32 | m_Attribute_0 |

## SimpleCommunity ([Structure])
| Type | Name |
| --- | --- |
| Uint32 | m_GatheringID |
| Uint32 | m_MatchmakeSessionCount |

[String]: NEX-Common-Types#string
[StationURL]: NEX-Common-Types#station-url
[List]: NEX-Common-Types#list
[PID]: NEX-Common-Types#pid
[Structure]: NEX-Common-Types#structure
[Buffer]: NEX-Common-Types#buffer
[DateTime]: NEX-Common-Types#date-time
[Map]: NEX-Common-Types#map
[Variant]: NEX-Common-Types#variant
[ResultRange]: NEX-Common-Types#result-range-structure
[Data]: NEX-Common-Types#any-data-holder

[MatchmakeSession]: #matchmakesession-structure
[Gathering]: #gathering-structure