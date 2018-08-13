## [[NEX Protocols]] > Account Management (0x19)

Most methods cannot be used by normal users.

| Method ID | Method Name |
| --- | --- |
| 1 | [CreateAccount](#1-createaccount) |
| 2 | [DeleteAccount](#2-deleteaccount) |
| 3 | [DisableAccount](#3-disableaccount) |
| 4 | [ChangePassword](#4-changepassword) |
| 5 | [TestCapability](#5-testcapability) |
| 6 | [GetName](#6-getname) |
| 7 | [GetAccountData](#7-getaccountdata) |
| 8 | [GetPrivateData](#8-getprivatedata) |
| 9 | [GetPublicData](#9-getpublicdata) |
| 10 | [GetMultiplePublicData](#10-getmultiplepublicdata) |
| 11 | [UpdateAccountName](#11-updateaccountname) |
| 12 | [UpdateAccountEmail](#12-updateaccountemail) |
| 13 | [UpdateCustomData](#13-updatecustomdata) |
| 14 | [FindByNameRegex](#14-findbynameregex) |
| 15 | [UpdateAccountExpiryDate](#15-updateaccountexpirydate) |
| 16 | [UpdateAccountEffectiveDate](#16-updateaccounteffectivedate) |
| 17 | [UpdateStatus](#17-updatestatus) |
| 18 | [GetStatus](#18-getstatus) |
| 19 | [GetLastConnectionStats](#19-getlastconnectionstats) |
| 20 | [ResetPassword](#20-resetpassword) |
| 21 | [CreateAccountWithCustomData](#21-createaccountwithcustomdata) |
| 22 | [RetrieveAccount](#22-retrieveaccount) |
| 23 | [UpdateAccount](#23-updateaccount) |
| 24 | [ChangePasswordByGuest](#24-changepasswordbyguest) |
| 25 | [FindByNameLike](#25-findbynamelike) |
| 26 | [CustomCreateAccount](#26-customcreateaccount) |
| 27 | [NintendoCreateAccount](#27-nintendocreateaccount) |
| 28 | [LookupOrCreateAccount](#28-lookuporcreateaccount) |
| 29 | [DisconnectPrincipal](#29-disconnectprincipal) |
| 30 | [DisconnectAllPrincipals](#30-disconnectallprincipals) |

# (1) CreateAccount
## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strPrincipalName | Username |
| [String] | strKey | See [key derivation](#key-derivation) |
| Uint32 | uiGroups | |
| [String] | strEmail | |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [Result] | %retval | Result code |

# (2) DeleteAccount
## Request
| Type | Name |
| --- | --- |
| [PID] | idPrincipal |

## Response
This method does not return anything.

# (3) DisableAccount
## Request
| Type | Name |
| --- | --- |
| [PID] | idPrincipal |
| [DateTime] | dtUntil |
| [String] | strMessage |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [Result] | %retval% | Result code |

# (4) ChangePassword
## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strNewKey | See [key derivation](#key-derivation) |

## Response
| Type | Name |
| --- | --- |
| Bool | %retval% |

# (5) TestCapability
## Request
| Type | Name |
| --- | --- |
| Uint32 | uiCapability |

## Response
| Type | Name |
| --- | --- |
| Bool | %retval% |

# (6) GetName
## Request
| Type | Name |
| --- | --- |
| [PID] | idPrincipal |

## Response
| Type | Name |
| --- | --- |
| [String] | strName |

# (7) GetAccountData
## Request
This method does not take any parameters

## Response
| Type | Name |
| --- | --- |
| Uint32 | %retval% |
| [AccountData](#accountdata) | oAccountData |

# (8) GetPrivateData
## Request
This method does not take any parameters.

## Response
| Type | Name |
| --- | --- |
| Bool | %retval% |
| [Data] | oData |

# (9) GetPublicData
## Request
| Type | Name |
| --- | --- |
| [PID] | idPrincipal |

## Response
| Type | Name |
| --- | --- |
| Bool | %retval% |
| [Data] | oData |

# (10) GetMultiplePublicData
## Request
| Type | Name |
| --- | --- |
| [List]&lt;[PID]&gt; | lstPrincipals |

## Response
| Type | Name |
| --- | --- |
| Bool | %retval% |
| [List]&lt;[Data]&gt; | oData |

# (11) UpdateAccountName
## Request
| Type | Name |
| --- | --- |
| [String] | strName |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [Result] | %retval% | Result code |

# (12) UpdateAccountEmail
## Request
| Type | Name |
| --- | --- |
| [String] | strName |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [Result] | %retval% | Result code |

# (13) UpdateCustomData
## Request
| Type | Name |
| --- | --- |
| [Data] | oPublicData |
| [Data] | oPrivateData |

## Response
| Type | Name | Description |
| --- | --- | --- |
| [Result] | %retval% | Result code |

# (14) FindByNameRegex
## Request
| Type | Name |
| --- | --- |
| Uint32 | uiGroups |
| [String] | strRegex |
| [ResultRange] | resultRange |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[BasicAccountInfo](#basicaccountinfo)&gt; | plstAccounts |

# (15) UpdateAccountExpiryDate
## Request
| Type | Name |
| --- | --- |
| [PID] | idPrincipal |
| [DateTime] | dtExpiry |
| [String] | strExpiredMessage |

## Response
This method does not return anything.

# (16) UpdateAccountEffectiveDate
## Request
| Type | Name |
| --- | --- |
| [PID] | idPrincipal |
| [DateTime] | dtEffectiveFrom |
| [String] | strNotEffectiveMessage |

## Response
This method does not return anything.

# (17) UpdateStatus
## Request
| Type | Name |
| --- | --- |
| [String] | strStatus |

## Response
This method does not return anything.

# (18) GetStatus
## Request
| Type | Name |
| --- | --- |
| [PID] | idPrincipal |

## Response
| Type | Name |
| --- | --- |
| [String] | strStatus |

# (19) GetLastConnectionStats
## Request
| Type | Name |
| --- | --- |
| [PID] | idPrincipal |

## Response
| Type | Name |
| --- | --- |
| [DateTime] | dtLastSessionLogin |
| [DateTime] | dtLastSessionLogout |
| [DateTime] | dtCurrentSessionLogin |

# (20) ResetPassword
## Request
This method does not take any parameters.

## Response
| Type | Name |
| --- | --- |
| Bool | %retval% |

# (21) CreateAccountWithCustomData
## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strPrincipalName | Username |
| [String] | strKey | See [key derivation](#key-derivation) |
| Uint32 | uiGroups | |
| [String] | strEmail | |
| [Data] | oPublicData | |
| [Data] | oPrivateData | |

## Response
This method does not return anything.

# (22) RetrieveAccount
## Request
This method does not take any parameters.

## Response
| Type | Name |
| --- | --- |
| [AccountData](#accountdata) | oAccountData |
| [Data] | oPublicData |
| [Data] | oPrivateData |

# (23) UpdateAccount
## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strKey | See [key derivation](#key-derivation) |
| [String] | strEmail | |
| [Data] | oPublicData | |
| [Data] | oPrivateData | |

## Response
This method does not return anything.

# (24) ChangePasswordByGuest
## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strPrincipalName | Username |
| [String] | strEmail | |
| [String] | strKey | See [key derivation](#key-derivation) |

## Response
This method does not return anything.

# (25) FindByNameLike
## Request
| Type | Name |
| --- | --- |
| Uint32 | uiGroups |
| [String] | strLike |
| [ResultRange] | resultRange |

## Response
| Type | Name |
| --- | --- |
| [List]&lt;[BasicAccountInfo](#basicaccountinfo)&gt; | plstAccounts |

# (26) CustomCreateAccount
## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strPrincipalName | Username |
| [String] | strKey | See [key derivation](#key-derivation) |
| Uint32 | uiGroups | |
| [String] | strEmail | |
| [Data] | oAuthData | |

## Response
| Type | Name |
| --- | --- |
| [PID] | pid |

# (27) NintendoCreateAccount
## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strPrincipalName | Username |
| [String] | strKey | See [key derivation](#key-derivation) |
| Uint32 | uiGroups | |
| [String] | strEmail | |
| [Data] | oAuthData | |

## Response
| Type | Name |
| --- | --- |
| [PID] | pid |
| [String] | pidHMAC |

# (28) LookupOrCreateAccount
## Request
| Type | Name | Description |
| --- | --- | --- |
| [String] | strPrincipalName | Username |
| [String] | strKey | See [key derivation](#key-derivation) |
| Uint32 | uiGroups | |
| [String] | strEmail | |
| [Data] | oAuthData | |

## Response
| Type | Name |
| --- | --- |
| [PID] | pid |

# (29) DisconnectPrincipal
## Request
| Type | Name |
| --- | --- |
| [PID] | idPrincipal |

## Response
| Type | Name |
| --- | --- |
| Bool | %retval% |

# (30) DisconnectAllPrincipals
## Request
This method does not take any parameters.

## Response
| Type | Name |
| --- | --- |
| Bool | %retval% |

# Key Derivation
Some functions take a key string. This is a hex string derived from the password using the following method:

| Platform | Method |
| --- | --- |
| 3DS / Wii U | MD5-hash the password 65000 times |
| Switch | MD5-hash the password once |

# Types
## BasicAccountInfo ([Structure])
| Type | Name |
| --- | --- |
| [PID] | m_pidOwner |
| [String] | m_strName |

## AccountData ([Structure])
| Type | Name |
| --- | --- |
| [PID] | m_pid |
| [String] | m_strName |
| Uint32 | m_uiGroups |
| [String] | m_strEmail |
| [DateTime] | m_dtCreationDate |
| [DateTime] | m_dtEffectiveDate |
| [String] | m_strNotEffectiveMsg |
| [DateTime] | m_dtExpiryDate |
| [String] | m_strExpiredMsg |

[Result]: NEX-Common-Types#result
[String]: NEX-Common-Types#string
[PID]: NEX-Common-Types#pid
[DateTime]: NEX-Common-Types#date-time
[Data]: NEX-Common-Types#any-data-holder
[List]: NEX-Common-Types#list
[ResultRange]: NEX-Common-Types#result-range-structure
[Structure]: NEX-Common-Types#structure
