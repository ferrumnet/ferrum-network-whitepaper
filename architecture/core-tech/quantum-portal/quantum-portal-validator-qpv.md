# 📝 Quantum Portal Validator (QPV)

## Quantum Portal Validator

1. Anyone can become a validator
2. Required to configure Ferrum Network node as QP Validator and stake at least 2,500,000 FRM (subject to change) on Ferrum Network. This will be broadcasted to all integrated networks.
3. Can finalize "mined blocks" but cannot mine new blocks
4. Can finalize blocks for multiple chains
5. The last action (finalizing a block) locks the stake for a month
6. Validators have the ability to slash miners if miners behave maliciously
7. Value Constrain Compliance can be overwritten by the Quantum Portal Validators

{% hint style="info" %}
**TODO:** Proof of malicious behavior of miners
{% endhint %}

## Who can become a Quantum Portal Validator?

Anyone can become a Quantum Portal Validator by configuring the Ferrum Network Node as a Quantum Portal Validator node which requires you to stake a minimum amount of tokens on the Ferrum Network. QPVs can validate transactions for multiple networks.

## What is Quantum Portal Validation?

The QP Validators take turns based on an algorithm to pick the pending (mined but not finalized) [Quantum Portal Blocks](quantum-portal-block.md) from the Quantum Portal Mined Block mempool. QP Validators do this by running the Ferrum Node as a QP Validator (QP Node). Once configured, this QP Node monitors the Quantum Portal Mined Block mempool for mined Quantum Portal Blocks, If new data is available, it creates a finalized block every 15 seconds. After creating a finalized block, the QP Node calls the `finalizeRemoteBlock` on the `destinationChain` in order to record the block as finalized and execute any remote transactions if applicable. The [QP Block](quantum-portal-block.md). It is considered a finalized block after the `finalizeRemoteBlock` transaction executes on the `destinationChain`

Once mined QP Blocks are finalized, the record of the finalized mined blocks and the finalized block itself is added to the `destinationChains`.

### A note about Finalizing Blocks

Finalizing of mined blocks cannot occur until a few threshold requirements are met. These requirements are hardcoded into the `quantumPortalContracts` on each chain. These requirements include:

1. Value Constrained Compliance
2. The time-limit threshold has reached&#x20;

If the above conditions are met, the mined Quantum Portal blocks can be finalized by Quantum Portal Validators.

## Validators can slash malicious [Quantum Portal Miners](quantum-portal-miner-qpm.md)

If a Quantum Portal Miner mines a block that is invalid. A threshold of validators will decide the mined block is invalid, they will submit proof of the invalid mined block and slash the miner. It should not be possible to mine invalid blocks unless acting maliciously, as the data is embedded into the on-chain transaction on the `sourceChain`.

{% hint style="warning" %}
**TODO:** Validator governance and compliance need to be finalized.
{% endhint %}

## Value Constrain Compliance can be overwritten by the Quantum Portal Validators

Value Constrained Compliant transactions only require a 33% validator threshold of signatures to be finalized and then broadcasted across the network. However, non-value-constrained compliant transactions require a 70% or higher validator threshold to be finalized as it is overwriting the Value Constrained requirement for Quantum Portal Miners.

{% hint style="danger" %}
**TODO:** If the majority of the validators collude, the network is at risk. Need to integrate ZK/optimistic proof. Integrate closely with relay chain governance.
{% endhint %}
