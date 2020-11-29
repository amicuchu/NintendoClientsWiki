## [NEX Protocols](NEX-Protocols.md) > Monitoring (0x13)

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

Mario Kart 8 Deluxe:
```
NGS_LP1_2B309E01-NODE0102 (master)
NGS_LP1_2B309E01-NODE0301
NGS_LP1_2B309E01-NODE0302
NGS_LP1_2B309E01-NODE0101
NGS_LP1_2B309E01-NODE0201
NGS_LP1_2B309E01-NODE0202
NGS_LP1_2B309E01-NODE0401
NGS_LP1_2B309E01-NODE0402
NGS_LP1_2B309E01-NODE0501
NGS_LP1_2B309E01-NODE0502
NGS_LP1_2B309E01-NODE0601
NGS_LP1_2B309E01-NODE0602
```

Super Mario Maker 1:
```
WUP_AMAJ-NODE0602 (master)
WUP_AMAJ-AUTH0201
WUP_AMAJ-NODE0101
WUP_AMAJ-AUTH0101
WUP_AMAJ-AUTH0301
WUP_AMAJ-AUTH0401
WUP_AMAJ-NODE0102
WUP_AMAJ-NODE0201
WUP_AMAJ-NODE0202
WUP_AMAJ-NODE0103
WUP_AMAJ-NODE0203
WUP_AMAJ-NODE0301
WUP_AMAJ-NODE0302
WUP_AMAJ-NODE0303
WUP_AMAJ-NODE0401
WUP_AMAJ-NODE0402
WUP_AMAJ-NODE0501
WUP_AMAJ-NODE0502
WUP_AMAJ-NODE0503
WUP_AMAJ-NODE0403
WUP_AMAJ-NODE0601
WUP_AMAJ-NODE0603
```

Super Mario Maker 2:
```
ip-10-7-2-135.us-west-2.compute.internal (master)
ip-10-7-9-250.us-west-2.compute.internal
ip-10-7-6-100.us-west-2.compute.internal
ip-10-7-11-76.us-west-2.compute.internal
ip-10-7-7-225.us-west-2.compute.internal
ip-10-7-11-237.us-west-2.compute.internal
ip-10-7-0-15.us-west-2.compute.internal
ip-10-7-11-205.us-west-2.compute.internal
ip-10-7-0-57.us-west-2.compute.internal
ip-10-7-0-14.us-west-2.compute.internal
ip-10-7-5-186.us-west-2.compute.internal
ip-10-7-6-132.us-west-2.compute.internal
ip-10-7-6-236.us-west-2.compute.internal
ip-10-7-3-237.us-west-2.compute.internal
ip-10-7-11-248.us-west-2.compute.internal
ip-10-7-5-90.us-west-2.compute.internal
ip-10-7-8-87.us-west-2.compute.internal
ip-10-7-6-207.us-west-2.compute.internal
ip-10-7-0-238.us-west-2.compute.internal
ip-10-7-10-154.us-west-2.compute.internal
ip-10-7-3-173.us-west-2.compute.internal
ip-10-7-7-143.us-west-2.compute.internal
ip-10-7-11-195.us-west-2.compute.internal
ip-10-7-3-154.us-west-2.compute.internal
ip-10-7-3-195.us-west-2.compute.internal
ip-10-7-10-18.us-west-2.compute.internal
ip-10-7-5-17.us-west-2.compute.internal
ip-10-7-3-139.us-west-2.compute.internal
ip-10-7-8-214.us-west-2.compute.internal
ip-10-7-5-75.us-west-2.compute.internal
ip-10-7-10-99.us-west-2.compute.internal
ip-10-7-5-147.us-west-2.compute.internal
ip-10-7-10-208.us-west-2.compute.internal
ip-10-7-8-237.us-west-2.compute.internal
ip-10-7-9-82.us-west-2.compute.internal
ip-10-7-2-59.us-west-2.compute.internal
ip-10-7-5-139.us-west-2.compute.internal
ip-10-7-1-86.us-west-2.compute.internal
ip-10-7-4-91.us-west-2.compute.internal
ip-10-7-11-201.us-west-2.compute.internal
ip-10-7-1-127.us-west-2.compute.internal
ip-10-7-11-21.us-west-2.compute.internal
ip-10-7-3-32.us-west-2.compute.internal
ip-10-7-5-236.us-west-2.compute.internal
ip-10-7-10-9.us-west-2.compute.internal
ip-10-7-3-136.us-west-2.compute.internal
ip-10-7-11-140.us-west-2.compute.internal
ip-10-7-3-160.us-west-2.compute.internal
ip-10-7-5-140.us-west-2.compute.internal
ip-10-7-6-99.us-west-2.compute.internal
ip-10-7-3-165.us-west-2.compute.internal
ip-10-7-1-20.us-west-2.compute.internal
ip-10-7-3-199.us-west-2.compute.internal
ip-10-7-10-87.us-west-2.compute.internal
ip-10-7-1-210.us-west-2.compute.internal
ip-10-7-6-252.us-west-2.compute.internal
ip-10-7-10-86.us-west-2.compute.internal
ip-10-7-7-115.us-west-2.compute.internal
ip-10-7-6-178.us-west-2.compute.internal
ip-10-7-4-131.us-west-2.compute.internal
ip-10-7-3-16.us-west-2.compute.internal
ip-10-7-0-95.us-west-2.compute.internal
ip-10-7-9-233.us-west-2.compute.internal
ip-10-7-6-107.us-west-2.compute.internal
ip-10-7-10-57.us-west-2.compute.internal
ip-10-7-1-102.us-west-2.compute.internal
ip-10-7-7-85.us-west-2.compute.internal
ip-10-7-0-76.us-west-2.compute.internal
ip-10-7-4-211.us-west-2.compute.internal
ip-10-7-11-77.us-west-2.compute.internal
ip-10-7-4-16.us-west-2.compute.internal
ip-10-7-3-20.us-west-2.compute.internal
ip-10-7-10-225.us-west-2.compute.internal
ip-10-7-7-188.us-west-2.compute.internal
ip-10-7-4-113.us-west-2.compute.internal
ip-10-7-0-62.us-west-2.compute.internal
ip-10-7-3-221.us-west-2.compute.internal
ip-10-7-8-252.us-west-2.compute.internal
ip-10-7-5-239.us-west-2.compute.internal
ip-10-7-10-63.us-west-2.compute.internal
ip-10-7-11-190.us-west-2.compute.internal
ip-10-7-10-158.us-west-2.compute.internal
ip-10-7-0-51.us-west-2.compute.internal
ip-10-7-7-32.us-west-2.compute.internal
ip-10-7-7-114.us-west-2.compute.internal
ip-10-7-2-130.us-west-2.compute.internal
ip-10-7-6-115.us-west-2.compute.internal
ip-10-7-6-223.us-west-2.compute.internal
ip-10-7-3-164.us-west-2.compute.internal
ip-10-7-2-51.us-west-2.compute.internal
ip-10-7-6-55.us-west-2.compute.internal
ip-10-7-4-188.us-west-2.compute.internal
ip-10-7-7-30.us-west-2.compute.internal
ip-10-7-0-80.us-west-2.compute.internal
ip-10-7-0-138.us-west-2.compute.internal
ip-10-7-11-161.us-west-2.compute.internal
ip-10-7-2-24.us-west-2.compute.internal
ip-10-7-10-127.us-west-2.compute.internal
ip-10-7-2-233.us-west-2.compute.internal
ip-10-7-8-15.us-west-2.compute.internal
ip-10-7-10-115.us-west-2.compute.internal
ip-10-7-0-42.us-west-2.compute.internal
ip-10-7-3-182.us-west-2.compute.internal
ip-10-7-7-138.us-west-2.compute.internal
ip-10-7-2-179.us-west-2.compute.internal
ip-10-7-4-171.us-west-2.compute.internal
ip-10-7-4-255.us-west-2.compute.internal
ip-10-7-9-100.us-west-2.compute.internal
ip-10-7-3-35.us-west-2.compute.internal
ip-10-7-8-50.us-west-2.compute.internal
ip-10-7-5-153.us-west-2.compute.internal
ip-10-7-10-5.us-west-2.compute.internal
ip-10-7-4-229.us-west-2.compute.internal
ip-10-7-10-83.us-west-2.compute.internal
ip-10-7-1-251.us-west-2.compute.internal
ip-10-7-0-184.us-west-2.compute.internal
ip-10-7-3-31.us-west-2.compute.internal
ip-10-7-6-219.us-west-2.compute.internal
ip-10-7-3-147.us-west-2.compute.internal
ip-10-7-10-48.us-west-2.compute.internal
ip-10-7-4-216.us-west-2.compute.internal
ip-10-7-5-115.us-west-2.compute.internal
ip-10-7-1-12.us-west-2.compute.internal
ip-10-7-0-78.us-west-2.compute.internal
ip-10-7-11-27.us-west-2.compute.internal
ip-10-7-9-183.us-west-2.compute.internal
ip-10-7-3-146.us-west-2.compute.internal
ip-10-7-3-166.us-west-2.compute.internal
ip-10-7-10-1.us-west-2.compute.internal
ip-10-7-10-175.us-west-2.compute.internal
ip-10-7-8-117.us-west-2.compute.internal
ip-10-7-1-254.us-west-2.compute.internal
ip-10-7-5-217.us-west-2.compute.internal
ip-10-7-11-241.us-west-2.compute.internal
ip-10-7-9-166.us-west-2.compute.internal
ip-10-7-6-117.us-west-2.compute.internal
ip-10-7-11-159.us-west-2.compute.internal
ip-10-7-3-204.us-west-2.compute.internal
ip-10-7-11-244.us-west-2.compute.internal
ip-10-7-8-84.us-west-2.compute.internal
ip-10-7-9-35.us-west-2.compute.internal
ip-10-7-8-107.us-west-2.compute.internal
ip-10-7-7-70.us-west-2.compute.internal
ip-10-7-2-178.us-west-2.compute.internal
ip-10-7-11-144.us-west-2.compute.internal
ip-10-7-8-174.us-west-2.compute.internal
ip-10-7-10-151.us-west-2.compute.internal
ip-10-7-5-46.us-west-2.compute.internal
ip-10-7-2-22.us-west-2.compute.internal
ip-10-7-10-17.us-west-2.compute.internal
ip-10-7-11-73.us-west-2.compute.internal
ip-10-7-10-97.us-west-2.compute.internal
ip-10-7-4-225.us-west-2.compute.internal
ip-10-7-8-97.us-west-2.compute.internal
ip-10-7-0-85.us-west-2.compute.internal
ip-10-7-9-244.us-west-2.compute.internal
ip-10-7-9-86.us-west-2.compute.internal
ip-10-7-11-102.us-west-2.compute.internal
ip-10-7-11-71.us-west-2.compute.internal
ip-10-7-7-231.us-west-2.compute.internal
ip-10-7-5-184.us-west-2.compute.internal
```

[List]: NEX-Common-Types.md#list
[String]: NEX-Common-Types.md#string