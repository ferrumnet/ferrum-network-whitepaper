# 👥 Multi-Chain Validators Staking

The Ferrum network quantum portal allows for multichain applications without the need for bridging and other wrapped assets. Quantum Portal is part of the Ferrum Runtime Node. When you deploy the Ferrum Network node, you can configure it to mine or validate Quantum Portal transactions of Ferrum Network transactions as a validator on the network. The QP ensures that the state of the bridged network is always available on the recipient network.

This means that the state of the source and destination chain is available on the Ferrum Network; now imagine a validator staking contract. Without the Quantum Portal, the user will have to stake on ChainA, then create a wrapped token to bridge to ChainB, but the rewards will not be transferred automatically; these will need to be separately bridged over later. The whole process is risky because the funds are secured by bridges.

With QP on the Ferum Network, the user can now validate on Chain A and then claim rewards on Chain B; this, of course, requires a Quantum Portal Smart Contract. Quantum Portal Smart Contracts (QPSC) are Permissionless, decentralized client-side entry points designed to enable interaction with the Ferrum Network and Quantum Portal nodes to conduct sophisticated multichain actions.

Quantum Portal Smart Contracts (QPSC) are designed to be generic by design. They are platform and chain agnostic. QPSC gives you the ability to conduct a `remoteTransaction` or check a `remoteBalance`.

Quantum Portal Mart Contracts (QPSC) and Quantum Portal Node Infrastructure, along with Ferrum Network nodes, adopt and implement the[ XCM](https://wiki.polkadot.network/docs/learn-xcm)
