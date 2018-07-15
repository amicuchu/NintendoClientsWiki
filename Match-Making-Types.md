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

[String]: NEX-Common-Types#string
[List]: NEX-Common-Types#list
[PID]: NEX-Common-Types#pid
[Structure]: NEX-Common-Types#structure
[Buffer]: NEX-Common-Types#buffer