# Blockchain Commons Torgap

### _by [Christopher Allen](@ChristopherA), [Peter Denton](@fonta1n3), and [Gorazd Kovacic](@gorazdko)_

![](images/logos/torgap-screen.jpg)

<img src="images/logos/torgap.png" align="right">

**Torgap** is the [Blockchain Commons](https://www.BlockchainCommons.com) architecture model for creating gaps between connected apps and microservices to support privacy, service anonymity, identity psuedonymity, non-correlation, and censorship-resistance, as well as offering seperation-of-interests and reduced single-points-of-failure.

## Example of Torgap Use

Here are the 2 Torgaps and 3 Airgaps in the current [Gordian](https://github.com/BlockchainCommons/Gordian) architecture:

<img src="https://raw.githubusercontent.com/BlockchainCommons/Gordian/master/Images/appmap.jpg" width="500" />

In this example:
* The remote iOS [Gordian Wallet](https://github.com/blockchainCommons/gordianwallet-ios) app talks to Mac [Gordian Server](https://github.com/BlockchainCommons/GordianServer-macOS) bitcoin full-node located at home, for confirming bitcoin transactions.
* The remote iOS [Gordian Wallet](https://github.com/blockchainCommons/gordianwallet-ios) app seperately talks to a Linux [Spotbit](https://github.com/BlockchainCommons/spotbit) server in the cloud, for aggregating bitcoin price information.

## Additional Information

The following files contain…

* **[Torgap FAQ](Docs/FAQ.md)** — More info on what Torgaps are and why they're useful.

## Torgap Repos

### Quick Connect

Quick Connect 1.0 is a specification that uses a QR-code to establish a Torgap link between a Gordian Wallet and a Bitcoin full node.

* **[Quick Connect 1.0 API](https://github.com/BlockchainCommons/Gordian/blob/master/Docs/Quick-Connect-API.md) \(specification\).** Connectivity specs.

We hope to extend the QuickConnect in version 2.0 to support links for multiple services in one QR code, to allow for multiple services like Bitcoin mainnet, testnet, and signet, as well as Lightning and SpotBit, as early demos of the capapabilities offered by Quick Connect 2.0's. This spec is in progress:

* **[Quick Connect 2.0 Requirements](https://github.com/BlockchainCommons/Airgapped-Wallet-Community/discussions)** Discussion.

### Gordian Server

Networked Gordian services and microservices connect to the Gordian Wallet via Torgaps.

* **[Gordian](https://github.com/BlockchainCommons/Gordian) \(wallet services\).** A walet system built around a Torgap between the Gordian Wallet and Gordian Server.
* **[spotBit](https://github.com/BlockchainCommons/spotbit) \(online server\).** A Bitcoin pricing microservice.

### Torgap Onion Repos

Torgap Onion is an experiment that combines `minisig` Ed25519 keys with Tor to enable `did:onion` DID and VC services over a a Torgap.

* **[torgap-demo](https://github.com/BlockchainCommons/torgap-demo) \(CLI demo\).** A demonstration of how `torgap-sig-cli-rust` can be used to verify a signature using an onion service, and offer a DID document.
  * **Live demo** [http://fscst5exmlmr262byztwz4kzhggjlzumvc2ndvgytzoucr2tkgxf7mid.onion/](http://fscst5exmlmr262byztwz4kzhggjlzumvc2ndvgytzoucr2tkgxf7mid.onion/)
  * **Simple onion-based [W3C DID](https://www.w3.org/TR/did-core/) (Decentralized Identifier) Document** [http://fscst5exmlmr262byztwz4kzhggjlzumvc2ndvgytzoucr2tkgxf7mid.onion/.well-known/did.json](http://fscst5exmlmr262byztwz4kzhggjlzumvc2ndvgytzoucr2tkgxf7mid.onion/.well-known/did.json).
  * **Linode Stackscript** A [Linode](https://www.linode.com/?r=23211828bc517e2cb36e0ca81b91cc8c0e1b2d96) installer [script](https://github.com/BlockchainCommons/torgap-demo/blob/master/StackScript/torgap-demo.sh) to automate installation of your own demo server and DID document using your own torgap keys.
* **[torgap-sig](https://github.com/BlockchainCommons/torgap-sig) \(Rust library\).** A fork of `rust-minisig` with support for Tor onion v3, testbedding `did:onion`, which enables DID and VCs lookups via a Torgap.
* **[torgap-sig-cli-rust](https://github.com/BlockchainCommons/torgap-sig-cli-rust) \(CLI tool\).** A fork of `rsign2` with support for Tor onion v3, with support for Tor onion v3, testbedding `did:onion:*`, which enables DID and VCs lookups via a Torgap.
* **[did-method-method](https://github.com/BlockchainCommons/did-method-onion)** A very preliminary [DID](https://www.w3.org/TR/did-core/) Method `did:onion:*` for using Tor onion transport and keys for the emerging [W3C Decentralized Identifier 1.0](https://www.w3.org/TR/did-core/) and [W3C Verifiable Credentials (VC) Data Model 1.0 ](https://www.w3.org/TR/vc-data-model/) standards.
* **[torgap-opentimestamps](https://github.com/BlockchainCommons/torgap-opentimestamps) \(Linode Stackscript\).** A [Linode](https://www.linode.com/?r=23211828bc517e2cb36e0ca81b91cc8c0e1b2d96) installer [script](https://github.com/BlockchainCommons/torgap-opentimestamps/blob/master/StackScript/torgap-opentimestamps.sh) to automate installation of OpenTimestamps (optionally with a Bitcoin full node verification) behind an onion service
  * **Live demo** [http://3xcaaswwserqnox56z7d7wifwyxm2jsdv4fniffym5jwncqx3qr7uzid.onion/]()

## Status - Varied

Please see individual repos for status.

## Origin, Authors, Copyright & Licenses

Unless otherwise noted (either in this [/README.md](./README.md) or in the file's header comments) the contents of this repository are Copyright © 2020 by Blockchain Commons, LLC, and are [licensed](./LICENSE) under the [spdx:BSD-2-Clause Plus Patent License](https://spdx.org/licenses/BSD-2-Clause-Patent.html).

In most cases, the authors, copyright, and license for each file reside in header comments in the source code. When it does not, we have attempted to attribute it accurately in the table below.

## Financial Support

TorGap is a project of [Blockchain Commons](https://www.blockchaincommons.com/). We are proudly a "not-for-profit" social benefit corporation committed to open source & open development. Our work is funded entirely by donations and collaborative partnerships with people like you. Every contribution will be spent on building open tools, technologies, and techniques that sustain and advance blockchain and internet security infrastructure and promote an open web.

To financially support further development of TorGap and other projects, please consider becoming a Patron of Blockchain Commons through ongoing monthly patronage as a [GitHub Sponsor](https://github.com/sponsors/BlockchainCommons). You can also support Blockchain Commons with bitcoins at our [BTCPay Server](https://btcpay.blockchaincommons.com/).

## Contributing

We encourage public contributions through issues and pull requests! Please review [CONTRIBUTING.md](./CONTRIBUTING.md) for details on our development process. All contributions to this repository require a GPG signed [Contributor License Agreement](./CLA.md).

### Discussions

The best place to talk about Blockchain Commons and its projects is in our GitHub Discussions areas.

[**Gordian System Discussions**](https://github.com/BlockchainCommons/Gordian/discussions). For users and developers of the Gordian system, including the Gordian Server, Bitcoin Standup technology, QuickConnect, and the Gordian Wallet. If you want to talk about our linked full-node and wallet technology, suggest new additions to our Bitcoin Standup standards, or discuss the implementation our standalone wallet, the Discussions area of the [main Gordian repo](https://github.com/BlockchainCommons/Gordian) is the place.

[**Wallet Standard Discussions**](https://github.com/BlockchainCommons/AirgappedSigning/discussions). For standards and open-source developers who want to talk about wallet standards, please use the Discussions area of the [Airgapped Signing repo](https://github.com/BlockchainCommons/AirgappedSigning). This is where you can talk about projects like our [LetheKit](https://github.com/BlockchainCommons/bc-lethekit) and command line tools such as [seedtool](https://github.com/BlockchainCommons/bc-seedtool-cli), both of which are intended to testbed wallet technologies, plus the libraries that we've built to support your own deployment of wallet technology such as [bc-bip39](https://github.com/BlockchainCommons/bc-bip39), [bc-slip39](https://github.com/BlockchainCommons/bc-slip39), [bc-shamir](https://github.com/BlockchainCommons/bc-shamir), [Shamir Secret Key Recovery](https://github.com/BlockchainCommons/bc-sskr), [bc-ur](https://github.com/BlockchainCommons/bc-ur), and the [bc-crypto-base](https://github.com/BlockchainCommons/bc-crypto-base). If it's a wallet-focused technology or a more general discussion of wallet standards,discuss it here.

[**Blockchain Commons Discussions**](https://github.com/BlockchainCommons/Community/discussions). For developers, interns, and patrons of Blockchain Commons, please use the discussions area of the [Community repo](https://github.com/BlockchainCommons/Community) to talk about general Blockchain Commons issues, the intern program, or topics other than the [Gordian System](https://github.com/BlockchainCommons/Gordian/discussions) or the [wallet standards](https://github.com/BlockchainCommons/AirgappedSigning/discussions), each of which have their own discussion areas.

### Other Questions & Problems

As an open-source, open-development community, Blockchain Commons does not have the resources to provide direct support of our projects. Please consider the discussions area as a locale where you might get answers to questions. Alternatively, please use this repository's [issues](./issues) feature. Unfortunately, we can not make any promises on response time.

If your company requires support to use our projects, please feel free to contact us directly about options. We may be able to offer you a contract for support from one of our contributors, or we might be able to point you to another entity who can offer the contractual support that you need.

### Credits

The following people directly contributed to this repository. You can add your name here by getting involved. The first step is learning how to contribute from our [CONTRIBUTING.md](./CONTRIBUTING.md) documentation.

| Name              | Role                | Github                                            | Email                                 | GPG Fingerprint                                    |
| ----------------- | ------------------- | ------------------------------------------------- | ------------------------------------- | -------------------------------------------------- |
| Christopher Allen | Principal Architect | [@ChristopherA](https://github.com/ChristopherA) | \<ChristopherA@LifeWithAlacrity.com\> | FDFE 14A5 4ECB 30FC 5D22  74EF F8D3 6C91 3574 05ED |
| Gorazd Kovacic | Lead Researcher | [@gorazdko](https://github.com/gorazdko) | \<gorazdko@gmail.com\> | 41F0 EA16 99A7 4C1E 2FA4 1B53 8CF9 6BC3 FF9D BBCE |


## Responsible Disclosure

We want to keep all of our software safe for everyone. If you have discovered a security vulnerability, we appreciate your help in disclosing it to us in a responsible manner. We are unfortunately not able to offer bug bounties at this time.

We do ask that you offer us good faith and use best efforts not to leak information or harm any user, their data, or our developer community. Please give us a reasonable amount of time to fix the issue before you publish it. Do not defraud our users or us in the process of discovery. We promise not to bring legal action against researchers who point out a problem provided they do their best to follow the these guidelines.

### Reporting a Vulnerability

Please report suspected security vulnerabilities in private via email to ChristopherA@BlockchainCommons.com (do not use this email for support). Please do NOT create publicly viewable issues for suspected security vulnerabilities.

The following keys may be used to communicate sensitive information to developers:

| Name              | Fingerprint                                        |
| ----------------- | -------------------------------------------------- |
| Christopher Allen | FDFE 14A5 4ECB 30FC 5D22  74EF F8D3 6C91 3574 05ED |

You can import a key by running the following command with that individual’s fingerprint: `gpg --recv-keys "<fingerprint>"` Ensure that you put quotes around fingerprints that contain spaces.
