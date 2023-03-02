---
description: Chain maximalism is so 2017! It's time to build a multi-chain future together.
---

# ⛓ Ferrum Runtime

The core Ferrum runtime specifies the state transition function and behavior of the Ferrum Network. Ferrum Runtime is built using[ the substrate FRAME pallets](https://docs.substrate.io/reference/frame-pallets/). By utilizing FRAME and relevant substrate pallets, we are able to take advantage of the work done by industry pioneers and focus on building our use case solutions instead of reinventing the wheel for basic runtime operations. We utilize a set of standard pallets and have created custom pallets to fit our use cases where applicable. We compile the runtime into a native and[ Wasm](https://webassembly.org/) binary. Utilizing the security of the relay chain the binaries are executed in Ferrum's node environment.

List of a few Substrate Frame Pallets utilized by Ferrum's runtime:

* **Balances —** Support for accounts, balances, and transfers
* **EVM —** Rust-based EVM implementation based on SputnikVM used for state transition logic for Ferrum Network-based smart contracts
* **Ethereum —** Provides emulation of Ethereum block processing for the EVM
* **RPC-Ethereum —** Web3 RPC implementation in Substrate
* **Council —** Includes governance mechanics around the council and proposals
* **Democracy —** Functionality for public stake-weighted token holder voting
* **Executive —** Orchestration layer that dispatches calls to other runtime modules
* **Indices —** Support for user-friendly short names for account addresses
* **System —** Provides low-level types, storage, and blockchain functions
* **Treasury —** On-chain treasury that can be used to fund public goods such as a parachain slot
* **Aura -** used to select block producers and validators for the network consensus.

## Ferrum Network's Key Technologies

The Ferrum network makes use of two cutting-edge technologies in the Substrate ecosystem to enable the functionality of our crosschain node.

## Offchain Workers

The blockchain runtime has to always remain deterministic; this has inherent limitations like the runtime cannot execute any non-deterministic tasks like an external API call. To overcome this, we use the substrate off-chain worker, Off-chain workers allow your Substrate node to offload tasks that take too long or too many CPU / memory resources to compute or have a non-deterministic result. In particular, there are a set of helpers allowing the fetching of HTTP requests and parsing for JSON. It also provides storage that is specific to the particular Substrate node and not shared across the network. Off-chain workers can also submit either signed or unsigned transactions back on-chain.

## Substrate Frontier

Frontier is Substrate's Ethereum compatibility layer. It allows you to run unmodified Ethereum dApps.

The goal of the Ethereum compatibility layer is to be able to:

* Run a normal web3 application via the compatibility layer, using local nodes, where an extra bridge binary is acceptable.
* Be able to import state from Ethereum mainnet.

Using substrate frontier allows the Ferrum node to utilize all the security aspects of the substrate and Polkadot ecosystem while still remaining fully compatible with any EVM chain. This allows developers to migrate their smart contracts from any evm chain to the Ferrum Network without any change.

\
