## [[NEX Protocols]] > Monitoring (0x13)

| Method ID | Method Name |
| --- | --- |
| 1 | PingDaemon |
| 2 | GetClusterMembers |

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