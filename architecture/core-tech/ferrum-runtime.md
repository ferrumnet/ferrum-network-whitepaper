---
description: Chain maximalism is so 2017! It's time to build a multi-chain future together.
---

# ⛓ Ferrum Runtime

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

We are also implementing additional modules with custom functionality for Ferrum Network to facilitate sophisticated developer tools, reward mechanisms, and to fulfill broadcasting needs.
