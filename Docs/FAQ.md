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

Tor is often used for its _identity pseudonymity_ : a client doesn't know who or what a server is, other than its onion address, and the converse is also true. This thwarts surveillance and enables privacy for the user. 

For users of the Tor browser, this means that web sites don't know who they are. Conversely, no one knows where a web site is or who's running it.

For users of other Tor hidden services, again the server can't track the user and the user can't track the server. Perhaps more importantly, there is strong _service anonymity_: third parties can't even see what services are being accessed, whereas the open internet would reveal that, even on an encrypted connection.

In addition, there are strong _non-correlation_ advantages. Web sites protected by Tor are all segregated, meaning that a user can't be tracked from one site to another, as occurs on the public web, using cookies and/or IP addresses. Similarly, usages of other hidden services can't be connected to each other. This non-correlation can also support _security_, though that requires a largely Tor-focused architecture, as is being created by Blockchain Commons.

### How Does Blockchain Commons Use Tor?

Blockchain Commons uses Tor to create Torgaps in its architectural designs, as described below.

However, Blockchain Commons also believes in open infrastructure, and so we have supported the Tor infrastructure itself. We run a Tor exit node [644074F47257F9A906F9AA5C6B8926C1540A1DA8](https://metrics.torproject.org/rs.html#details/644074F47257F9A906F9AA5C6B8926C1540A1DA8), and we are working on Tor-related tools that we will give back to the Tor community.

## Torgap Overview

### What is Torgap?

Torgap is the creation of a Tor-protocol link between a client and a server that work together as part of a larger system.

At this time, Blockchain Commons is primarily using Torgaps as part of its Gordian system, isolating clients, servers, and microservices with Torgaps.

![](https://raw.githubusercontent.com/BlockchainCommons/Gordian/master/Images/appmap.jpg)

Torgap are usually not built around web services, but instead are links for services of other types.

### What is the Torgap Architecture?

The Torgap Archicture is a the creation of a network of distributed systems that are linked together via Torgaps rather than the open or TLS-encrypted connections that are more common on the internet.

A Torgap Architecture may also include Airgaps, when even higher levels of security or privacy are required.

### How is Torgap Different from Airgap?

An Airgap is divide between two services with no network connection. It is usually bridged via the photographing of QR codes or the entry of short lines of text.

A Torgap is a Tor link between two connected nework services. It introduces various Tor-related advantages for situations where the full advantages of an Airgap are impractical.

### What are the Adventages of the Torgap Architecture?

The biggest advantage of the Torgap architecture comes from _service anonymity_. If you are using the Gordian system, snoopers won't know that you're accessing Bitcoin services such as a full-node or the [Spotbit](https://github.com/BlockchainCommons/spotbit) pricing service. This can be critically important in a State that is hostile to digital currencies, as is important anywhere.

That's because many [#SmartCustody Adversaries](https://github.com/BlockchainCommons/SmartCustodyBook) arise from the loss of privacy. If people don't know you're using Bitcoin, they often can't steal it from you. The _identity pseudonymity_ of the Torgap architecture is an important advantage for the same reason.

Finally, the Torgap architecture is able to leverage new _security_ in several ways.

To start with, the Torgap architecture allows us to leave behind the legacy security of certs and cert authorities, instead utilizing the security of Tor itself. This takes away the threats of compromised (or malicious) authorities, and also improves the archiecture's _non-correlation_: now, attackers can't even correlate your usage of certificates on the internet.

In addition, because the Torgap architecture creates a map of isolated microservices, there are no large honeypots in the system. The fall of an individual service, like a SpotBit service, reveals very limited information about the digital-asset system as a whole.

This all goes back to the _non-correlation_ advantage: no one knows who anyone else is, nor what else they're doing (with the exception of a user's Gordian Wallet, which is very secure as a mobile device). This means that attacks on individual services reveal nothing about the system as a whole, nor how it connects up.

The ultimate goal os the Torgap architecture is to separate keys and processes in secure ways, to allow people to protect their virtual selves and assets.

## Torgap Services

### How is Torgap Used in the Gordian System?

Currently, there are two Torgaps in the Gordian system, as shown in the app map, above. The mobile Gordian Wallet and the full-node Gordian Server are connected by a Torgap. There is also a Torgap between the Gordian Wallet and our first microservice, the Spotbit pricing server.

### What is QuickConnect?

The QuickConnect API is a simple specification for linking a Bitcoin hidden service with a wallet client using a URL and an associated scannable QR code. It's used in the Gordian system to create the Torgap between the Gordian Wallet and a full node such as the Gordian Server.

### What Are the Advantages of Using Torgap in Gordian?

Creating a Torgap between your Wallet and your full-node ensures that no one can see that you're interacting with the Bitcoin network. It also helps to protect your keys: the Gordian system secures your bitcoins with a 2-of-3 multi-sig, with one key on your server and one in your wallet. Thanks to the non-correlation of Torgaps, finding one key tells an attacker nothing about where the other key is located.

Tor has traditionally ben an underused option for Bitcoin, but an option nonetheless: it's built into Bitcoin Core. However, the same can't be said for other Bitcoin services. In particular, pricing services were a strong vulnerability because there was no easy way to look up Bitcoin prices via Tor. The Torgap to Spotbit introduces that possibility for the first time, ensuring the total _service anonymity_ of your Bitcoin usage.

### How is Torgap Used with DIDs & VCs?

### What are the Advantages of Using Torgap with DIDs & VCs?

## Torgap Futures

### What is the Future of Torgap?
