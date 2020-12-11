# Torgap FAQ
<img src="../images/logos/torgap.png" align="right">

## Table of Contents

* [Tor Overview](#tor-overview)
* [Torgap Overview](#torgap-overview)
* [Torgap Services](#torgap-services)
* [Torgap Futures](#torgap-futures)

## Tor Overview

### What is the Tor Protocol?

Tor is short for "The Onion Router". It's a protocol that allows for the anonymous access of internet services: users submit and receive data from [`hidden services`](##what-is-a-hidden-service), with that data being encrypted multiple times and routed through multiple Tor servers. As a result, the data is protected from exposure and both the client and the server enjoy strong pseudonymity.

### What is the Tor Browser?

The most common usage of the [`Tor protocol`](#what-is-the-tor-protocol) is to access websites pseudonymously in a hidden, _non-correlated_ way. This is typically done through the [tor browser](https://www.torproject.org/download/).

### What is a Hidden Service?

A hidden service (also known as an "anonymous onion service") is an internet service that's reachable through the [`Tor protocol`](#what-is-the-tor-protocol). These services are not limited to web pages, but could include anything, such as a smarthome control panel, a mail POP service, or a stock-price lookup API.

### What is Tor v3 Client Auth?

Client authorization is a feature added with Tor v3. It uses public-key cryptography: a public key is stored on the server offering the hidden service, then a client connects with the corresponding private key. In order for the client to access the service, the keys must match.

### What are the Advantages of Tor?

Tor is often used for its _identity pseudonymity_ : a client doesn't know who or what a server is, other than its onion address, and the converse is also true. This thwarts surveillance and enables privacy for the user. 

For users of the Tor browser, this means that web sites don't know who they are, and users don't know where a web site is. Perhaps more importantly, third-party eavesdroppers can't see what site the end-user is accessing.

For users of other Tor hidden services, again the server can't track the user and the user can't track the server. There is also strong _service anonymity_: third parties can't even see what services are being accessed, whereas the open internet would reveal that, even on an encrypted connection.

In addition, there are strong _non-correlation_ advantages. Web sites protected by Tor are all segregated, meaning that a user can't be tracked from one site to another, as occurs on the public web using cookies and/or IP addresses. Similarly, the uage of other hidden services can't be connected to each other. This non-correlation can also support _security_, though that requires a largely Tor-focused architecture, as is being created by Blockchain Commons.

### How Does Blockchain Commons Use Tor?

Blockchain Commons uses Tor to create [`Torgaps`](#what-is-torgap) in its architectural designs, as described below.

However, Blockchain Commons also believes in open infrastructure, and so we have supported the Tor infrastructure itself. We run a Tor _exit node_, [644074F47257F9A906F9AA5C6B8926C1540A1DA8](https://metrics.torproject.org/rs.html#details/644074F47257F9A906F9AA5C6B8926C1540A1DA8), and we are working on Tor-related tools that we will give back to the Tor community.

## Torgap Overview

### What is Torgap?

A Torgap is a [`Tor-protocol`](#what-is-the-tor-protocol) link between a client and a server, that is a part of a larger system.

At this time, Blockchain Commons is primarily using Torgaps as part of its Gordian system, to isolate clients, servers, and microservices:

![](https://raw.githubusercontent.com/BlockchainCommons/Gordian/master/Images/appmap.jpg)

Torgaps are usually not built around web services, but (as in our Gordian System) are instead links for services of other types.

### What is the Torgap Architecture?

The Torgap Archicture is the creation of a network of distributed systems that are linked together via Torgaps rather than the open or TLS-encrypted connections that are more common on the internet.

A Torgap Architecture may also include _Airgaps_, when even higher levels of security or privacy are required.

### How is Torgap Different from Airgap?

An Airgap is a divide between two services with no network connection. It is usually bridged via the photographing of QR codes or the entry of short lines of text.

A Torgap is a Tor link between two connected nework services, used when an Airgap is impractical.

### What are the Adventages of the Torgap Architecture?

The biggest advantage of the Torgap architecture comes from _service anonymity_. If you are using the [Gordian system](https://github.com/BlockchainCommons/Gordian), third-party _eavesdroppers_ won't know that you're accessing Bitcoin services such as a full-node or the [Spotbit](https://github.com/BlockchainCommons/spotbit) pricing service. This can be critically important in a State that is hostile to digital currencies ... but is important everywhere. That's because many [#SmartCustody Adversaries](https://github.com/BlockchainCommons/SmartCustodyBook) arise from the loss of privacy: if attackers don't know you're using Bitcoin, they often can't steal it from you. The _identity pseudonymity_ of the Torgap architecture is an important advantage for the same reason.

The Torgap architecture is also able to leverage new _security_ in several ways.

To start with, the Torgap architecture leaves behind the legacy security of _certs_ and _cert authorities_, instead utilizing the security of Tor itself. This removes the threat of compromised (or malicious) authorities and also improves the archiecture's non-correlation: now, attackers can't even correlate your usage of certificates on the internet.

In addition, because the Torgap architecture is built upon maps of isolated microservices, there are no large honeypots in the system. The imaginary fall of an individual service, like a SpotBit service, will reveal very limited information about the digital-asset system as a whole.

The _non-correlation_ itself is also a large advantage: no one knows who anyone else is, nor what else they're doing (with the exception of a user's Gordian Wallet, which is physically secured). This means that attacks on individual services reveal nothing about the system as a whole, nor how it connects up.

The ultimate goal of the Torgap architecture is to separate keys and processes in secure ways, and to allow people to protect their virtual selves and assets.

## Torgap Services

### How is Torgap used in the Gordian System?

Currently, there are two Torgaps in the [Gordian system](https://github.com/BlockchainCommons/Gordian), as shown in the app map, above. The mobile [Gordian Wallet](https://github.com/BlockchainCommons/GordianWallet-iOS) and the full-node [Gordian Server](https://github.com/BlockchainCommons/GordianServer-macOS) are connected by a Torgap. There is also a Torgap between the Gordian Wallet and our first microservice, the [Spotbit pricing server](https://github.com/BlockchainCommons/spotbit).

### What is QuickConnect?

The [QuickConnect 1.0 API](https://github.com/BlockchainCommons/Gordian/blob/master/Docs/Quick-Connect-API.md) is a simple specification for linking a Bitcoin hidden service with a wallet client using a URL and an associated scannable QR code. It's used in the Gordian system to create the Torgap between the Gordian Wallet and a full node such as the Gordian Server. A more generalized Quick Connect 2.0 is being [discussed](https://github.com/BlockchainCommons/Airgapped-Wallet-Community/discussions/33).

### What Are the Advantages of Using Torgap in the Gordian System?

Creating a Torgap between your Wallet and your full-node ensures that no one can see that you're interacting with the Bitcoin network. It also helps to protect your keys: the Gordian system secures your bitcoins with a 2-of-3 multi-sig, with one key on your server and one in your wallet. Thanks to the non-correlation of Torgaps, finding one key tells an attacker nothing about where the other key is located.

Tor has traditionally been an underused option for Bitcoin, but a usefull option nonetheless: it's built into Bitcoin Core. However, the same can't be said for other Bitcoin services. In particular, pricing services have long been a vulnerability because there was no easy way to look up Bitcoin prices via Tor. The Torgap to Spotbit introduces that possibility for the first time, ensuring the total _service anonymity_ of your Bitcoin usage.

### How is Torgap Used with DIDs & VCs?

Blockchain Commons is experimenting with a provisional `did:onion` [DID method](https://github.com/blockchainCommons/did-method-onion). This DID method uses the [W3C Decentralized Identifiers (DIDs) 1.0](https://www.w3.org/TR/did-core/) and [W3C Verifiable Credentials (VC) Data Model 1.0](https://www.w3.org/TR/vc-data-model/) standards to allow holders of credentials & claims to reference, resolve and retrieve a DID documents anonymously through a Torgap. These can then be used to verify those credentials, other claims (such as reviews), as well as future sophisticated objects such as authorization capability tokens.

See the [torgap-sig-cli repo](https://github.com/BlockchainCommons/torgap-sig-cli-rust) for more information about our research.

### What are the Advantages of Using Torgap with DIDs & VCs?

More privacy. Using DIDs and VCs allows everyone to be pseudonymous. Someone can own a public, networked DID without there being any hint as to who they are. Similarly, someone can make Verifiable Claims without revealing their identity.

However, the most important gains may come for the end-user. They can look up DIDs and Verifiable Claims without revealing who they are. This is a big change from the _un-gapped_ world: before, authorities could see that you were interested in verifying a signature or referencing a claim, possibly revealing information about who you are and what you're planning to do; now, you can do so without revealing that information.

Example: Most other data verification architectures (and some other DID methods) suffer from a "phone home" problem where holders of data needing verification of data, and then reveal their interest in that data. For instance, after the recent Apple Big Sur OS release, it was [revealed](https://sneak.berlin/20201112/your-computer-isnt-yours/) that your Mac communicates with Apple whenever you open a new app. This addresses a legitimate need for Apple to ban malicious applications and developers. However, this request reveals that you have attempted to install an app by that developer. Using `did:onion` the party requesting validation of an app would not be correlatable with the device or user requesting it.

## Torgap Futures

### What is the Future of Torgap?

Torgaps can be used anywhere it's useful to partition off a service. Doing so will accumulate the privacy, security, and non-correlation advantages implicitly in this architectural approach, but Torgaps can also support impoved seperation-of-interests, and partition off single points of failure.

Blockchain Commons plans to investigate a number of other examples of Torgap-based microservices. In addition to existing Torgaps between Bitcoin wallets & full-nodes (Quick Connect), and our Bitcoin Wallet and price discovery (SpotBit), these are just some of the early ideas for

* Lightning Network (C-Lighting & LND)
* Blockchain Explorers (in particular Esplora for Bitcoin)
* Transaction Coordinators
* Coinjoin & Cryptocurrency Privacy Services
* 2FA & Multisig Agents
* Sharded Key Storage
* Secure Chat & Forwarding Services
* Paid Data Services (possibly throug Lightning-based LSATs)
* Confidential Data Stores

If you have other ideas for how to use a Torgap, join in the discussion in the [Airgapped Wallet Community](https://github.com/BlockchainCommons/Airgapped-Wallet-Community/discussions/34).

If you'd like to see these future projects come to life, we need your support. We are funded entirely by patronage, donations, and collaborative partnerships with people like you. Please consider becoming a [GitHub Sponsor](https://github.com/sponsors/BlockchainCommons) or by making a donation at btcpay.blockchaincommons.com.
