# 📐 Overview

### Background and Overview

The value proposition and use case for Ferrum's mainnet has evolved since Ferrum's inception in 2018. As the crypto landscape evolves, the team at Ferrum Network has dedicated tremendous effort to ensure that the Ferrum Network mainnet continues to adapt and evolve to provide limitless utility and value to all stakeholders.&#x20;

### Ferrum Network Tech Stack Overview

![Ferrum Network Mainnet Tech Stack Overview v0.1.8](<../../.gitbook/assets/Ferrum Network Mainnet Tech Stack Overview v0.1.8.gif>)

### The Core Stack

Ferrum mainnet is developed in [_RUST_](https://www.rust-lang.org/) using the [Substrate Framework](https://substrate.io/). Ferrum Network will be deployed as a parachain on the Polkadot Relay chain after securing a parachain slot through the [Polkadot Parachain Auction process](https://parachains.info/auctions).&#x20;

#### The Chain

Ferrum Network is a Turing complete blockchain with a smart contract-enabled platform. The chain is responsible for facilitating use cases such as the Quantum Portal, FIBER, FORGE, and limitless other use cases to be developed by Ferrum and open-source contributors in the future. The validation of transactions and their immutability is secured by the Polkadot Relay chain.&#x20;

We have made significant efforts to simplify our implementation ensuring easy extensibility and further development of the network itself as well as deployment of dApps and solutions on the network.

### Ferrum Runtime <a href="#blockchain-runtime" id="blockchain-runtime"></a>

The core Ferrum runtime specifies the state transition function and behavior of the Ferrum Network. Ferrum Runtime is built using [FRAME pallets](https://docs.substrate.io/reference/frame-pallets/). By utilizing FRAME and relevant substrate pallets, we are able to take advantage of the work done by industry pioneers and focus on building our use case solutions instead of reinventing the wheel for basic runtime operations. We utilize a set of standard pallets and have created custom pallets to fit our use cases where applicable. We compile the runtime into a native and [Wasm](https://webassembly.org/) binary. Utilizing the security of the relay chain the binaries are executed in Ferrum's node environment and Polkadot's relay chain.

List of a few Substrate Frame Pallets utilized by Ferrum's runtime:

* **Balances** — Support for accounts, balances, and transfers
* **EVM** — Rust-based EVM implementation based on SputnikVM used for state transition logic for Ferrum Network-based smart contracts
* **Ethereum** — Provides emulation of Ethereum block processing for the EVM
* **RPC-Ethereum** — Web3 RPC implementation in Substrate
* **Council** — Includes governance mechanics around the council and proposals
* **Democracy** — Functionality for public stake-weighted token holder voting
* **Executive** — Orchestration layer that dispatches calls to other runtime modules
* **Indices** — Support for user-friendly short names for account addresses
* **System** — Provides low-level types, storage, and blockchain functions
* **Treasury** — On-chain treasury that can be used to fund public goods such as a parachain slot

We also utilize the [Cumulus library](https://github.com/paritytech/cumulus) by Parity to integrate with the Polkadot relay chain.

We are also implementing additional modules with custom functionality for Ferrum Network to facilitate developer tools, reward mechanisms, and fulfill broadcasting needs.
