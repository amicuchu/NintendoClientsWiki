## Boxcat

Since the release of the Nintendo Switch, nintendo replaced spotpass and notifications by a new service called Boxcat which is sometimes is named bcat as a short form. This service uses a special file containers called BCAT containers which can wrap any form of file or messagepack formated data. Boxcat distributes 2 types of content, one called data which are savedatas that targeted game can access after being synced and news which appear in the news section inside qlaunch(Main menu applet)

#### Servers involved

Domain name | Description
--- | ---
`bcat-data-<enviroment>.cdn.nintendo.nintendo.net` | This domain contains the content which is directly delivered to intended applications
`bcat-topics-<enviroment>.cdn.nintendo.nintendo.net` | This domain contains the topics avaiable including a description of it, the topics related to an application and a list of all news
`bcat-list-<enviroment>.cdn.nintendo.nintendo.net` | This domain contains the listings that describe which content is avaiable to applications and how is presented inside filesystem hierarcy

#### Bcat container kinds

Kind | URL where appears | Description
--- | --- | ---
Data | `https://bcat-data-<enviroment>.cdn.nintendo.nintendo.net/api/nx/v1/data` | The data that is delivered to applications
News | `https://bcat-data-<enviroment>.cdn.nintendo.nintendo.net/api/nx/v1/news` | The standalone complete news
News summary | `https://bcat-data-<enviroment>.cdn.nintendo.nintendo.net/api/nx/v2/news_summaries` | A fragment of a certain news enough to represent it in a list
List | `https://bcat-list-<enviroment>.cdn.nintendo.nintendo.net/api/nx/v1/list` | A list of data containers which composes the filesystem presented to the application
Title | `https://bcat-topics-<enviroment>.cdn.nintendo.nintendo.net/api/nx/v1/titles` | Contains the name of the topic associated to an application
Topic details | `https://bcat-topics-<enviroment>.cdn.nintendo.nintendo.net/api/nx/v1/topics/<topic id>/detail` | Description of a topic
Topic icon | `https://bcat-topics-<enviroment>.cdn.nintendo.nintendo.net/api/nx/v1/topics/<topic id>/icon` | Icon of a topic
Catalog | `https://bcat-topics-<enviroment>.cdn.nintendo.nintendo.net/api/nx/v1/topics/catalog` | The list of avaiable topics
Online archive | `https://bcat-topics-<enviroment>.cdn.nintendo.nintendo.net/api/nx/v2/topics/` | List of news summaries avaiable for a topic

*Paths in the previous table aren't complete, refer to individual pages of every kind*

#### Flow diagram

![Bcat Flow](bcat%20flow.png)

#### Bcat passphrase

The bcat containers are encrypted with a key that depends of a 64 character hexadecimal string called passphrase, this passphrase can be found in the [NACP](https://switchbrew.org/wiki/NACP_Format) of the application which bcat container targets. All containers related to news use the passphrase of qlaunch system application

#### Subscriptions

The news section shows news from topics which the user account is subscripted. By default, users are subscripted to `nx_news` and `nx_notice`, the first topic contains news about Nintendo and the shop and the second one contains news about new features avaiable in modern firmwares. The user can subscribe using the news section which reads the list of topics provided by the catalog or running a new application that has a topic related in form of a bcat title.

The subscriptions to lists that contain data are automatically controlled by bcat sysmodule acording to what applications are avaiable in the system. Subscriptions are managed using XMPP subscription messages inside NPNS