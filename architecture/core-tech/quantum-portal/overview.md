# 📐 Overview

Quantum Portal is part of the Ferrum Runtime Node. When you deploy the Ferrum Network node you can configure it to mine or validate Quantum Portal transactions of Ferrum Network transactions as a validator on the network.

Quantum Portal includes the following core components:

1. [Quantum Portal Node](overview.md#quantum-portal-node)
2. [Quantum Portal Smart Contracts](overview.md#quantum-portal-smart-contracts)
3. [Quantum Portal MultiChain Explorer](overview.md#quantum-portal-multichain-explorer)

<img src="../../../.gitbook/assets/file.drawing (1).svg" alt="Quantum Portal Overview Flow" class="gitbook-drawing">

<figure><img src="../../../.gitbook/assets/Quantum Portal is part of the Ferrum Runtime Node. v3 - Taha Abbasi.png" alt=""><figcaption><p>Quantum Portal Overview Flow</p></figcaption></figure>

Let's explore each of these components in some detail.

## Quantum Portal Node (QPN)

A Quantum Portal Node is essentially a Ferrum Network configured as a Quantum Portal miner or validator. There are different requirements to run a QP Miner or QP Validator node. These are covered in the linked pages below. Depending on how the Quantum Portal Node is configured, it will interact with either the [Quantum Portal Smart Contracts](overview.md#quantum-portal-smart-contracts) to mine Quantum Portal Blocks or with the mined blocks and Quantum Portal Smart Contracts to finalize mined blocks.

{% content-ref url="quantum-portal-miner-qpm.md" %}
[quantum-portal-miner-qpm.md](quantum-portal-miner-qpm.md)
{% endcontent-ref %}

{% content-ref url="quantum-portal-validator-qpv.md" %}
[quantum-portal-validator-qpv.md](quantum-portal-validator-qpv.md)
{% endcontent-ref %}

## Quantum Portal Smart Contracts (QPSC)

Quantum Portal Smart Contracts are deployed on each integrated chain and serve as the client-side interface for interacting with the [Quantum Portal Nodes](overview.md#quantum-portal-node) to execute any MultiChain transaction or query. Additionally, QPSCs provide the data necessary for [QP Miners](quantum-portal-miner-qpm.md) to create and mine [QP Blocks](quantum-portal-blocks-qpb.md) and provide a mechanism for [QP Validators](quantum-portal-validator-qpv.md) to finalize mined QP Blocks.

Learn more about Quantum Portal Smart Contracts (QPSC) on the dedicated page linked below.

{% content-ref url="quantum-portal-smart-contracts-qpsc.md" %}
[quantum-portal-smart-contracts-qpsc.md](quantum-portal-smart-contracts-qpsc.md)
{% endcontent-ref %}

## Quantum Portal MultiChain Explorer (QPME)

The Quantum Portal MultiChain Explorer provides an interface that brings together information from various components of the Quantum Portal infrastructure, including Quantum Portal Smart Contracts, Quantum Portal Nodes, and MultiChain transactional data. Learn more about the details of QPME on the dedicated page linked below.

{% content-ref url="quantum-portal-multichain-explorer-qpme.md" %}
[quantum-portal-multichain-explorer-qpme.md](quantum-portal-multichain-explorer-qpme.md)
{% endcontent-ref %}
