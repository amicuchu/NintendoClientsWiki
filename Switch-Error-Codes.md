# Error Categories
| Error Codes | Description |
| --- | --- |
| 2306-XXXX | [NEX (game servers)](#nex-error-codes)<br>[Error descriptions](#nex-error-descriptions) |
| 2618-XXXX | PIA (peer to peer) |
| 2815-XXXX | [Coral (voice chat)](#coral-error-codes) |

# NEX Error Codes
| Error code | Name |
| --- | --- |
| 2306-0102 | Core::Unknown |
| 2306-0103 | Core::NotImplemented |
| 2306-0104 | Core::InvalidPointer |
| 2306-0105 | Core::OperationAborted |
| 2306-0106 | Core::Exception |
| 2306-0107 | Core::AccessDenied |
| 2306-0108 | Core::InvalidHandle |
| 2306-0109 | Core::InvalidIndex |
| 2306-0110 | Core::OutOfMemory |
| 2306-0111 | Core::InvalidArgument |
| 2306-0112 | Core::Timeout |
| 2306-0113 | Core::InitializationFailure |
| 2306-0114 | Core::CallInitiationFailure |
| 2306-0115 | Core::RegistrationError |
| 2306-0116 | Core::BufferOverflow |
| 2306-0117 | Core::InvalidLockState |
| 2306-0118 | Core::InvalidSequence |
| 2306-0119 | Core::SystemError |
| 2306-0120 | Core::Cancelled |
| 2306-0201 | DDL::InvalidSignature |
| 2306-0202 | DDL::IncorrectVersion |
| 2306-0301 | RendezVous::ConnectionFailure |
| 2306-0302 | RendezVous::NotAuthenticated |
| 2306-0302 | RendezVous::InvalidUsername |
| 2306-0303 | RendezVous::InvalidPassword |
| 2306-0304 | RendezVous::UsernameAlreadyExists |
| 2306-0305 | RendezVous::AccountDisabled |
| 2306-0306 | RendezVous::AccountExpired |
| 2306-0307 | RendezVous::ConcurrentLoginDenied |
| 2306-0308 | RendezVous::EncryptionFailure |
| 2306-0309 | RendezVous::InvalidPID |
| 2306-0310 | RendezVous::MaxConnectionsReached |
| 2306-0311 | RendezVous::InvalidGID |
| 2306-0312 | RendezVous::InvalidControlScriptID |
| 2306-0313 | RendezVous::InvalidOperationInLiveEnvironment |
| 2306-0314 | RendezVous::DuplicateEntry |
| 2306-0315 | RendezVous::ControlScriptFailure |
| 2306-0316 | RendezVous::ClassNotFound |
| 2306-0317 | RendezVous::SessionVoid |
| 2306-0319 | RendezVous::DDLMismatch |
| 2306-0320 | RendezVous::InvalidConfiguration |
| 2306-0322 | RendezVous::SessionFull |
| 2306-0323 | RendezVous::InvalidGatheringPassword |
| 2306-0324 | RendezVous::WithoutParticipationPeriod |
| 2306-0325 | RendezVous::PersistentGatheringCreationMax |
| 2306-0326 | RendezVous::PersistentGatheringParticipationMax |
| 2306-0327 | RendezVous::DeniedByParticipants |
| 2306-0328 | RendezVous::ParticipantInBlackList |
| 2306-0329 | RendezVous::GameServerMaintenance |
| 2306-0330 | RendezVous::OperationPostpone |
| 2306-0331 | RendezVous::OutOfRatingRange |
| 2306-0332 | RendezVous::ConnectionDisconnected |
| 2306-0333 | RendezVous::InvalidOperation |
| 2306-0334 | RendezVous::NotParticipatedGathering |
| 2306-0335 | RendezVous::MatchmakeSessionUserPasswordUnmatch |
| 2306-0336 | RendezVous::MatchmakeSessionSystemPasswordUnmatch |
| 2306-0337 | RendezVous::UserIsOffline |
| 2306-0338 | RendezVous::AlreadyParticipatedGathering |
| 2306-0339 | RendezVous::PermissionDenied |
| 2306-0340 | RendezVous::NotFriend |
| 2306-0341 | RendezVous::SessionClosed |
| 2306-0342 | RendezVous::DatabaseTemporarilyUnavailable |
| 2306-0343 | RendezVous::InvalidUniqueId |
| 2306-0344 | RendezVous::MatchmakingWithdrawn |
| 2306-0345 | RendezVous::LimitExceeded |
| 2306-0346 | RendezVous::AccountTemporarilyDisabled |
| 2306-0347 | RendezVous::PartiallyServiceClosed |
| 2306-0348 | RendezVous::ConnectionDisconnectedForConcurrentLogin |
| 2306-0401 | PythonCore::Exception |
| 2306-0402 | PythonCore::TypeError |
| 2306-0403 | PythonCore::IndexError |
| 2306-0404 | PythonCore::InvalidReference |
| 2306-0405 | PythonCore::CallFailure |
| 2306-0406 | PythonCore::MemoryError |
| 2306-0407 | PythonCore::KeyError |
| 2306-0408 | PythonCore::OperationError |
| 2306-0409 | PythonCore::ConversionError |
| 2306-0410 | PythonCore::ValidationError |
| 2306-0501 | Transport::Unknown |
| 2306-0502 | Transport::ConnectionFailure |
| 2306-0503 | Transport::InvalidUrl |
| 2306-0504 | Transport::InvalidKey |
| 2306-0505 | Transport::InvalidURLType |
| 2306-0506 | Transport::DuplicateEndpoint |
| 2306-0507 | Transport::IOError |
| 2306-0508 | Transport::Timeout |
| 2306-0509 | Transport::ConnectionReset |
| 2306-0510 | Transport::IncorrectRemoteAuthentication |
| 2306-0511 | Transport::ServerRequestError |
| 2306-0512 | Transport::DecompressionFailure |
| 2306-0513 | Transport::ReliableSendBufferFullFatal |
| 2306-0514 | Transport::UPnPCannotInit |
| 2306-0515 | Transport::UPnPCannotAddMapping |
| 2306-0516 | Transport::NatPMPCannotInit |
| 2306-0517 | Transport::NatPMPCannotAddMapping |
| 2306-0519 | Transport::UnsupportedNAT |
| 2306-0520 | Transport::DnsError |
| 2306-0521 | Transport::ProxyError |
| 2306-0522 | Transport::DataRemaining |
| 2306-0523 | Transport::NoBuffer |
| 2306-0524 | Transport::NotFound |
| 2306-0525 | Transport::TemporaryServerError |
| 2306-0526 | Transport::PermanentServerError |
| 2306-0527 | Transport::ServiceUnavailable |
| 2306-0528 | Transport::ReliableSendBufferFull |
| 2306-0529 | Transport::InvalidStation |
| 2306-0530 | Transport::InvalidSubStreamID |
| 2306-0531 | Transport::PacketBufferFull |
| 2306-0532 | Transport::NatTraversalError |
| 2306-0533 | Transport::NatCheckError |
| 2306-0602 | DOCore::StationNotReached |
| 2306-0603 | DOCore::TargetStationDisconnect |
| 2306-0604 | DOCore::LocalStationLeaving |
| 2306-0605 | DOCore::ObjectNotFound |
| 2306-0606 | DOCore::InvalidRole |
| 2306-0607 | DOCore::CallTimeout |
| 2306-0608 | DOCore::RMCDispatchFailed |
| 2306-0609 | DOCore::MigrationInProgress |
| 2306-0610 | DOCore::NoAuthority |
| 2306-0611 | DOCore::NoTargetStationSpecified |
| 2306-0612 | DOCore::JoinFailed |
| 2306-0613 | DOCore::JoinDenied |
| 2306-0614 | DOCore::ConnectivityTestFailed |
| 2306-0615 | DOCore::Unknown |
| 2306-0616 | DOCore::UnfreedReferences |
| 2306-0617 | DOCore::JobTerminationFailed |
| 2306-0618 | DOCore::InvalidState |
| 2306-0619 | DOCore::FaultRecoveryFatal |
| 2306-0620 | DOCore::FaultRecoveryJobProcessFailed |
| 2306-0621 | DOCore::StationInconsitency |
| 2306-0622 | DOCore::AbnormalMasterState |
| 2306-0623 | DOCore::VersionMismatch |
| 2306-0701 | FPD::NotInitialized |
| 2306-0702 | FPD::AlreadyInitialized |
| 2306-0703 | FPD::NotConnected |
| 2306-0704 | FPD::Connected |
| 2306-0705 | FPD::InitializationFailure |
| 2306-0706 | FPD::OutOfMemory |
| 2306-0707 | FPD::RmcFailed |
| 2306-0708 | FPD::InvalidArgument |
| 2306-0709 | FPD::InvalidLocalAccountID |
| 2306-0710 | FPD::InvalidPrincipalID |
| 2306-0711 | FPD::InvalidLocalFriendCode |
| 2306-0712 | FPD::LocalAccountNotExists |
| 2306-0713 | FPD::LocalAccountNotLoaded |
| 2306-0714 | FPD::LocalAccountAlreadyLoaded |
| 2306-0715 | FPD::FriendAlreadyExists |
| 2306-0716 | FPD::FriendNotExists |
| 2306-0717 | FPD::FriendNumMax |
| 2306-0718 | FPD::NotFriend |
| 2306-0719 | FPD::FileIO |
| 2306-0720 | FPD::P2PInternetProhibited |
| 2306-0721 | FPD::Unknown |
| 2306-0722 | FPD::InvalidState |
| 2306-0724 | FPD::AddFriendProhibited |
| 2306-0726 | FPD::InvalidAccount |
| 2306-0727 | FPD::BlacklistedByMe |
| 2306-0729 | FPD::FriendAlreadyAdded |
| 2306-0730 | FPD::MyFriendListLimitExceed |
| 2306-0731 | FPD::RequestLimitExceed |
| 2306-0732 | FPD::InvalidMessageID |
| 2306-0733 | FPD::MessageIsNotMine |
| 2306-0734 | FPD::MessageIsNotForMe |
| 2306-0735 | FPD::FriendRequestBlocked |
| 2306-0736 | FPD::NotInMyFriendList |
| 2306-0737 | FPD::FriendListedByMe |
| 2306-0738 | FPD::NotInMyBlacklist |
| 2306-0739 | FPD::IncompatibleAccount |
| 2306-0740 | FPD::BlockSettingChangeNotAllowed |
| 2306-0741 | FPD::SizeLimitExceeded |
| 2306-0742 | FPD::OperationNotAllowed |
| 2306-0743 | FPD::NotNetworkAccount |
| 2306-0744 | FPD::NotificationNotFound |
| 2306-0745 | FPD::PreferenceNotInitialized |
| 2306-0746 | FPD::FriendRequestNotAllowed |
| 2306-1101 | Ranking::NotInitialized |
| 2306-1102 | Ranking::InvalidArgument |
| 2306-1103 | Ranking::RegistrationError |
| 2306-1105 | Ranking::NotFound |
| 2306-1106 | Ranking::InvalidScore |
| 2306-1107 | Ranking::InvalidDataSize |
| 2306-1109 | Ranking::PermissionDenied |
| 2306-1110 | Ranking::Unknown |
| 2306-1111 | Ranking::NotImplemented |
| 2306-0801 | Authentication::NASAuthenticateError |
| 2306-0802 | Authentication::TokenParseError |
| 2306-0803 | Authentication::HttpConnectionError |
| 2306-0804 | Authentication::HttpDNSError |
| 2306-0805 | Authentication::HttpGetProxySetting |
| 2306-0806 | Authentication::TokenExpired |
| 2306-0807 | Authentication::ValidationFailed |
| 2306-0808 | Authentication::InvalidParam |
| 2306-0809 | Authentication::PrincipalIdUnmatched |
| 2306-0810 | Authentication::MoveCountUnmatch |
| 2306-0811 | Authentication::UnderMaintenance |
| 2306-0812 | Authentication::UnsupportedVersion |
| 2306-0813 | Authentication::ServerVersionIsOld |
| 2306-0814 | Authentication::Unknown |
| 2306-0815 | Authentication::ClientVersionIsOld |
| 2306-0816 | Authentication::AccountLibraryError |
| 2306-0817 | Authentication::ServiceNoLongerAvailable |
| 2306-0818 | Authentication::UnknownApplication |
| 2306-0819 | Authentication::ApplicationVersionIsOld |
| 2306-0820 | Authentication::OutOfService |
| 2306-0821 | Authentication::NetworkServiceLicenseRequired |
| 2306-0822 | Authentication::NetworkServiceLicenseSystemError |
| 2306-0823 | Authentication::NetworkServiceLicenseError3 |
| 2306-0824 | Authentication::NetworkServiceLicenseError4 |
| 2306-1201 | DataStore::Unknown |
| 2306-1202 | DataStore::InvalidArgument |
| 2306-1203 | DataStore::PermissionDenied |
| 2306-1204 | DataStore::NotFound |
| 2306-1205 | DataStore::AlreadyLocked |
| 2306-1206 | DataStore::UnderReviewing |
| 2306-1207 | DataStore::Expired |
| 2306-1208 | DataStore::InvalidCheckToken |
| 2306-1209 | DataStore::SystemFileError |
| 2306-1210 | DataStore::OverCapacity |
| 2306-1211 | DataStore::OperationNotAllowed |
| 2306-1212 | DataStore::InvalidPassword |
| 2306-1213 | DataStore::ValueNotEqual |
| 2306-1500 | ServiceItem::Unknown |
| 2306-1501 | ServiceItem::InvalidArgument |
| 2306-1502 | ServiceItem::EShopUnknownHttpError |
| 2306-1503 | ServiceItem::EShopResponseParseError |
| 2306-1504 | ServiceItem::NotOwned |
| 2306-1505 | ServiceItem::InvalidLimitationType |
| 2306-1506 | ServiceItem::ConsumptionRightShortage |
| 2306-1801 | MatchmakeReferee::Unknown |
| 2306-1802 | MatchmakeReferee::InvalidArgument |
| 2306-1803 | MatchmakeReferee::AlreadyExists |
| 2306-1804 | MatchmakeReferee::NotParticipatedGathering |
| 2306-1805 | MatchmakeReferee::NotParticipatedRound |
| 2306-1806 | MatchmakeReferee::StatsNotFound |
| 2306-1807 | MatchmakeReferee::RoundNotFound |
| 2306-1808 | MatchmakeReferee::RoundArbitrated |
| 2306-1809 | MatchmakeReferee::RoundNotArbitrated |
| 2306-1901 | Subscriber::Unknown |
| 2306-1902 | Subscriber::InvalidArgument |
| 2306-1903 | Subscriber::OverLimit |
| 2306-1904 | Subscriber::PermissionDenied |
| 2306-2001 | Ranking2::Unknown |
| 2306-2002 | Ranking2::InvalidArgument |
| 2306-2003 | Ranking2::InvalidScore |
| 2306-2201 | Screening::Unknown |
| 2306-2202 | Screening::InvalidArgument |
| 2306-2203 | Screening::NotFound |

# NEX Error Descriptions
| Error&nbsp;code | Description |
| --- | --- |
| 2306-0102 | The reason for the error is unknown. |
| 2306-0103 | The operation is currently not implemented. |
| 2306-0104 | The operation specifies or accesses an invalid pointer. |
| 2306-0105 | The operation was aborted. |
| 2306-0106 | The operation raised an exception. |
| 2306-0107 | An attempt was made to access data in an incorrect manner. This may be due to inadequate permission or the data, file, etc. not existing. |
| 2306-0108 | The operation specifies or accesses an invalid DOHandle. |
| 2306-0109 | The operation specifies or accesses an invalid index. |
| 2306-0110 | The system could not allocate or access enough memory or disk space to perform the specified operation. |
| 2306-0111 | Invalid argument were passed with the operation. The argument(s) may be out of range or invalid. |
| 2306-0112 | The operation did not complete within the specified timeout for that operation. |
| 2306-0113 | Initialization of the component failed. |
| 2306-0114 | The call failed to initialize. |
| 2306-0115 | An error occurred during registration. |
| 2306-0116 | The buffer is too large to be sent. |
| 2306-0301 | Connection was unable to be established, either with the Rendez-Vous back end or a Peer. |
| 2306-0302 | The Principal could not be authenticated by the Authentication Service. |
| 2306-0303 | The Principal tried to log in with an invalid user name, i.e. the user name does not exist in the database. |
| 2306-0304 | The Principal either tried to log in with an invalid password for the provided user name or tried to join a Gathering with an invalid password. |
| 2306-0305 | The provided user name already exists in the database. All usernames must be unique. |
| 2306-0306 | The Principal's account still exists in the database but the account has been disabled. |
| 2306-0307 | The Principal's account still exists in the database but the account has expired. |
| 2306-0308 | The Principal does not have the Capabilities to perform concurrent log ins, i.e. at any given time only one log-in may be maintained. |
| 2306-0309 | Data encryption failed. |
| 2306-0310 | The operation specifies or accesses an invalid PrincipalID. |
| 2306-0311 | Maximum connnection number is reached |
| 2306-0501 | The reason for the error is unknown. |
| 2306-0502 | Network connection was unable to be established. |
| 2306-0503 | The URL contained in the StationURL is invalid. The syntax may be incorrect. |
| 2306-0504 | The key used to authenticate a given station is invalid. The secure transport layer uses secret-key based cryptography to ensure the integrity and confidentiality of data sent across the network. |
| 2306-0505 | The specified transport type is invalid. |
| 2306-0506 | The Station is already connected via another EndPoint. |
| 2306-0507 | The data coudl not be sent across the network. This could be due to an invalid message, packet, or buffer. |
| 2306-0508 | The operation did not complete within the specified timeout for that operation. |
| 2306-0509 | The network connection was reset. |
| 2306-0510 | The destination Station did not authenticate itself properly. |
| 2306-0511 | 3rd-party server or device answered with an error code according to protocol used e.g. HTTP error code |

# Coral Error Codes
| Error code | Name |
| --- | --- |
| 2815-2101 | SmartDeviceVoiceChat::Unknown |
| 2815-2102 | SmartDeviceVoiceChat::InvalidArgument |
| 2815-2103 | SmartDeviceVoiceChat::InvalidResponse |
| 2815-2104 | SmartDeviceVoiceChat::InvalidAccessToken |
| 2815-2105 | SmartDeviceVoiceChat::Unauthorized |
| 2815-2106 | SmartDeviceVoiceChat::AccessError |
| 2815-2107 | SmartDeviceVoiceChat::UserNotFound |
| 2815-2108 | SmartDeviceVoiceChat::RoomNotFound |
| 2815-2109 | SmartDeviceVoiceChat::RoomNotActivated |
| 2815-2110 | SmartDeviceVoiceChat::ApplicationNotSupported |
| 2815-2111 | SmartDeviceVoiceChat::InternalServerError |
| 2815-2112 | SmartDeviceVoiceChat::ServiceUnavailable |
| 2815-2113 | SmartDeviceVoiceChat::UnexpectedError |
| 2815-2114 | SmartDeviceVoiceChat::UnderMaintenance |
| 2815-2115 | SmartDeviceVoiceChat::ServiceNoLongerAvailable |
| 2815-2116 | SmartDeviceVoiceChat::AccountTemporarilyDisabled |
| 2815-2117 | SmartDeviceVoiceChat::PermissionDenied |
| 2815-2118 | SmartDeviceVoiceChat::NetworkServiceLicenseRequired |
| 2815-2119 | SmartDeviceVoiceChat::AccountLibraryError |
| 2815-2120 | SmartDeviceVoiceChat::GameModeNotFound |