# Securing the Network

Ferrum network would be launched as a parachain on the Polkadot network. This means that the Ferrum network is secured by the shared security model of the Polkadot relay chain.

## Definition of a Parachain[​](https://wiki.polkadot.network/docs/learn-parachains#definition-of-a-parachain)

A parachain is an application-specific data structure that is globally coherent and can be validated by the validators of the Relay Chain. They take their name from the concept of parallelized chains that run parallel to the Relay Chain. Most commonly, a parachain will take the form of a blockchain, but there is no specific need for them to be actual blockchains.

<figure><img src="https://lh5.googleusercontent.com/Yo1woBjcYc53OAptwfYO5UC9HVzrpu6JnX9_X6hz5DAvVyfEdgnVlQCS9lMF2hAC0igfZoZ51t3wKGC_rIDZaw5Nlr_vIndNd44_S8AOEaIcizgoTZ17JXEhZffb63UKLqVe9U4I2KFw4jPemyc9XnU" alt=""><figcaption><p>Image : Polkadot Network</p></figcaption></figure>

## Shared Security[​](https://wiki.polkadot.network/docs/learn-parachains#shared-security)

Shared security, sometimes referred to in documentation as pooled security, is one of the unique value propositions for chains considering becoming a [parachain](https://wiki.polkadot.network/docs/learn-parachains) and joining the Polkadot network. On a high level, shared security means that all parachains that are connected to the Polkadot Relay Chain by leasing a parachain slot will benefit from the economic security provided by the Relay Chain [validators](https://wiki.polkadot.network/docs/learn-validator).

The notion of shared security is different from inter-chain protocols that build on an architecture of bridges. For bridge protocols, each chain is considered sovereign and must maintain its own validator set and economic security. One concern in these protocols is on the point of scalability of security. For example, one suggestion to scale blockchains is that of scale by altcoins, which suggests that transaction volumes will filter down to lower market cap altcoins as the bigger ones fill their blocks. A major flaw in this idea is that the lower market cap coins will have less economic security attached, and be easier to attack. A real life example of a 51% attack occurred recently ( [Ethereum Classic attack on January 10, 2019](https://cointelegraph.com/news/ethereum-classic-51-attack-the-reality-of-proof-of-work) ), in which an unknown attacker double spent 219\_500 ETC (\~1.1 million USD). This was followed by two more 51% attacks on ETC.

Polkadot overcomes security scalability concerns since it gravitates all the economic incentives to the Relay Chain and allows the parachains to tap into stronger guarantees at genesis. Sovereign chains must expend much more effort to grow the value of their coin so that it is sufficiently secure against well-funded attackers.

## Resources[​](https://wiki.polkadot.network/docs/learn-parachains#resources)

* [Polkadot: The Parachain](https://medium.com/polkadot-network/polkadot-the-parachain-3808040a769a) - Blog post by Polkadot co-founder Rob Habermeier who introduced parachains in 2017 as "a simpler form of blockchain, which attaches to the security provided by a Relay Chain rather than providing its own. The Relay Chain provides security to attached parachains, but also provides a guarantee of secure message-passing between them."
* [The Path of a Parachain Block](https://polkadot.network/the-path-of-a-parachain-block/) - A technical walk-through of how parachains interact with the Relay Chain.
