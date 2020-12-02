# Torgap FAQ
<img src="../images/logos/torgap.png" align="right">

## Tor Overview

### What is the Tor Protocol?

Tor is short for "The Onion Router". It's a protocol that allows for the anonymous access of internet services: users submit and receive data from hidden services, with that data being multiply encrypted and routed through multiple Tor servers. The result is that the data is protected from exposure and both the client and the server enjoy strong pseuodnymity.

### What is the Tor Browser?

The most common usage of the Tor protocol is to access websites anonymously in a hidden, non-correlated way. This is typically done through the [tor browser](https://www.torproject.org/download/).

### What is a Hidden Service?

A hidden service (also known as an "anonymous onion service") is an internet service that's reachable through the Tor protocol. It is not limited to web pages, but could be anything, such as a smarthome control panel, a mail POP service, or a stock-price lookup API.

### What is Tor v3 Client Auth?

Client authorization is a featured added with Tor v3. It uses public-key cryptography: a public key is stored on the server offering the hidden service, then a client connects with the corresponding private key. In order for the client to access the service, the keys must match.

### What are the Advantages of Tor?

Tor is often used for its _anonymity_ advantages — though it would be better to call it _pseudonymity_: a client doesn't know who or what a server is, other than its onion address, and the converse is also true. This thwarts surveillance and enables privacy for the user. 

For users of the Tor browser, this means that web sites don't know who they are. Conversely, no one knows where a web site is or who's running it.

For users of other Tor hidden services, again the server can't track the user and the user can't track the server.

In addition, there are strong _non-correlation_ advantages. Web sites protected by Tor are all segregated, meaning that a user can't be tracked from one site to another, as occurs on the public web, using cookies and/or IP addresses. Similarly, usages of other hidden services can't be connected to each other. This non-correlation can also support _security_, though that requires a largely Tor-focused architecture, as is being created by Blockchain Commons.

### How Does Blockchain Commons Use Tor?

Blockchain Commons uses Tor to create Torgaps in its architectural designs, as described below.

However, Blockchain Commons also believes in open infrastructure, and so we have supported the Tor infrastructure itself. We run a Tor exit node [644074F47257F9A906F9AA5C6B8926C1540A1DA8](https://metrics.torproject.org/rs.html#details/644074F47257F9A906F9AA5C6B8926C1540A1DA8), and we are working on Tor-related tools that we will give back to the Tor community.

## Torgap Overview

### What is Torgap?

Torgap is the creation of a Tor-protocol link between a client and a server that work together as part of a larger system.

At this time, Blockchain Commons is primarily using Torgaps as part of its Gordian system, isolating clients, servers, and microservices with Torgaps.

![](https://raw.githubusercontent.com/BlockchainCommons/Gordian/master/Images/appmap.jpg)

### What is the Torgap Architecture?

The Torgap Archicture is a the creation of a network of distributed systems that are linked together via Torgaps rather than the open or TLS-encrypted connections that are more common on the internet.

### How is Torgap Different from Airgap?

### What are the Adventages of the Torgap Architecture?

[primarily hidden services, not necessarily web browsers, but other services]

[no legacy technologies like certs which can create correlation]

[can leverage security of channel, using onion security]

[can use things other than CA as ways of authenticating]


--

[no tor browser, not that side of things, 
[allowing of separation of keys & process in secure ways to allow people to protect their virtual selves

--


## Torgap Services

### How is Torgap Used in the Gordian System?

### What is QuickConnect?

### What Are the Advantages of Using Torgap in Gordian?

### How is Torgap Used with DIDs & VCs?

### What are the Advantages of Using Torgap with DIDs & VCs?


## Torgap Futures

### What is the Future of Torgap?
