NEX is a network library that provides various services, like rankings, match making and a data store.

Before connecting to a game server, a NEX token is requested from the account server, which contains the ip and port of the game server, your pid and NEX password, and a token that can be passed to [TicketGrantingProtocol](Authentication-Protocol)::[LoginEx](Authentication-Protocol#2-loginex).

NEX uses a [remote method call protocol](RMC-Protocol) to call methods on various [services](NEX-Protocols).