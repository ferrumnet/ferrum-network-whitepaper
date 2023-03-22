---
description: >-
  Learn how Ferrum's tech is simplifying interactions with multiple chains for
  developers, project owners and community members
---

# 🗺 10,000 Foot View – A gateway to the multichain future

## A gateway to building multichain

Ferrum Network's mission is to make multichain interactions as easy as deploying a token contract on Ethereum. Ferrum Network is banking on Polkadot's bet against chain maximalism as we dive into an increasingly multichain future. To ensure the success of these unique chains with their unique value propositions, Ferrum Network is building technology to make multichain development, interaction, and integration as seamless as deploying a simple token contract on Ethereum. We are using the following core segments to accomplish our mission.

1. Ecosystem agnostic BPM (Blockchain Package Manager) for web3
2. Vetted RPC and Infrastructure partners for each integrated chain
3. Tech tools, demo dApps, scripts, and guides to "build once and deploy everywhere"
4. Developer support and consistent updates based on developer feedback

## Ecosystem agnostic BPM (Blockchain Package Manager) for web3

### Background and Inspiration from NPMs success

One of the main reasons Javascript, specifically the [MEAN](https://en.wikipedia.org/wiki/MEAN\_\(solution\_stack\)) and [MERN](https://www.mongodb.com/mern-stack) stacks, have taken off in popularity over the last decade is the extensive availability of reusable vetted code packages accessible through [NPM](https://en.wikipedia.org/wiki/Npm\_\(software\)). A fantastic example of this in web2 is the Express framework built on top of Node.js. Express is designed to help developers easily manage servers, routes, build, SPAs, and even Multi-Page applications. With Express available through NPM, a developer doesn't have to create this functionality on his own; they can run the following [command to install Express](https://expressjs.com/en/starter/installing.html):

```sh
$ npm install express
```

Of course, this assumes the developer already has [Node.js](https://nodejs.org/en) installed and has [initialized NPM](https://expressjs.com/en/starter/installing.html).

With a simple command, a powerful library is available to start the management of servers, routes, and so much more. As of today, it is the most popular [Node.js](https://nodejs.org/en) framework, with over [2.15 million websites and apps](https://trends.builtwith.com/framework/Express) around the world currently using it. This is incredibly powerful; it means that in building these 2.15 million applications, tens of millions of developers saved countless hours by using the Express framework to manage servers, routes, and build their applications. Furthermore, this reusability enabled these developers to focus on their application's core and unique feature development instead of building the basic foundation of the application.

### A package manager for web3 – BPM

Ferrum Network is facilitating the creation of BPM (Blockchain Package Manager) to accomplish the same goal as NPM. Save developers countless hours of repetitive work and provide an organized registry of safe, vetted code that can help create the foundational structure of a web3 dApp across networks. There are solutions like Substrate by Polkadot and even solutions in the Cosmos ecosystem, but these solutions remain platform dependant. Ferrum is utilizing these powerful solutions and adding a layer of interoperability to them. Based on the Substrate pallet-based framework, we are creating a set of tools and supporting infrastructure that will enable developers to focus on building unique core features of their dApp instead of wasting their time figuring out why a specific RPC endpoint isn't working for their dApp. We hope to take the friction of multichain web3 development away by providing solutions for issues like:&#x20;

> Hmm...why is my [EIP-712](https://eips.ethereum.org/EIPS/eip-712) signature hashing scheme working on network a (EVM Compatible) but not network b (Non-EVM compatible)

It takes quite a bit of effort for developers to learn that the architecture they have applied on one chain isn't supported on another. For most standard dApps, Ferrum intends to solve this out of the box. For custom use cases, Ferrum is building tooling, guidance, and solutions for developers to create alternative solutions for problems like the EIP-712 issue described above.

## Vetted RPC and Infrastructure partners for each integrated chain

<figure><img src="../../.gitbook/assets/Vetted RPC and Infrastructure partners for each integrated chain V2.png" alt=""><figcaption><p>Ureliable RPC Infrastructure</p></figcaption></figure>

It's near impossible to build any dApp without reliable RPC infrastructure in place. Even if it's a set of a few nodes in the beginning, providing a reliable way to extract and submit data to the network is essential to enabling the development of dApps on the chain. Many chains have less than desirable reliability for their RPC infrastructure, and in many cases, they are not yet supported by major RPC providers. So developers have to play a game of Whac-A-Mole to figure out which provided endpoint will work. Even the ones working sometimes tend to go offline. Ferrum Network carefully works with layer 1 chains themselves to ensure reliable RPC infrastructure is in place. In cases where problems with infrastructure are evident, Ferrum Network provides guidance and, on some occasions, alternate solutions to developers.&#x20;

## Tech tools, demo dApps, scripts, and guides to "build once and deploy everywhere"

There are solutions like [OpenZeppelin](https://www.openzeppelin.com/), which have done a great service to the industry already with reusable, vetted standardized code snippets and their wizard tool for modifying some of these standard cases. Ferrum Network is amplifying this work across EVM and non-EVM networks and adding an interactive layer by giving developers solutions like the Multichain Token Standard, Multichain Staking, and much more. We are empowering developers with the technical guides, tooling, and infrastructure to start deploying multichain dApps right away. Our base tooling is Substrate based, and we intend to utilize the Substrate Pallet framework to offer an increasing number of reusable pallets to the community of builders around web3.

## Developer support and consistent updates based on developer feedback

Without ongoing iterative improvements, most initiatives are doomed to fail. Ferrum actively seeks developer and builder feedback to incorporate improvements, sort out bugs, and add new enhancements to our available toolset. We prioritize developer relations and support as one of the most important elements of our success. This includes support from the Ferrum Engineering team, as well as support from other engineers in building multichain dApps utilizing the Ferrum-provided technology solutions and tooling.

