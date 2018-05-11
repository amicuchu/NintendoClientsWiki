## [[NEX Protocols]] > Monitoring (0x13)

| Method ID | Method Name |
| --- | --- |
| 1 | [PingDaemon](#1-pingdaemon) |
| 2 | [GetClusterMembers](#2-getclustermembers) |

# (1) PingDaemon
## Request
This method does not take any parameters

## Response
| Type | Name | Description |
| --- | --- | --- |
| Bool | %retval% | Result |

# (2) GetClusterMembers
## Request
This method does not take any parameters.

## Response
| Type | Name | Description |
| --- | --- | --- |
| [List]&lt;[String]&gt; | strValues | Cluster node names |

Example response from Mario Kart 8 Deluxe:

```['NGS_LP1_2B309E01-NODE0102 (master)', 'NGS_LP1_2B309E01-NODE0301', 'NGS_LP1_2B309E01-NODE0302', 'NGS_LP1_2B309E01-NODE0101', 'NGS_LP1_2B309E01-NODE0201', 'NGS_LP1_2B309E01-NODE0202', 'NGS_LP1_2B309E01-NODE0401', 'NGS_LP1_2B309E01-NODE0402', 'NGS_LP1_2B309E01-NODE0501', 'NGS_LP1_2B309E01-NODE0502', 'NGS_LP1_2B309E01-NODE0601', 'NGS_LP1_2B309E01-NODE0602']```

[List]: NEX-Common-Types#list
[String]: NEX-Common-Types#string