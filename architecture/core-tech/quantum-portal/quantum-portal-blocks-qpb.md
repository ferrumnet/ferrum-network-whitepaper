# 🧱 Quantum Portal Blocks (QPB)

There are two types of Quantum Portal Blocks.&#x20;

1. Standard Blocks
2. Finalized Blocks

## Standard Quantum Portal Blocks (standardQPB)

Standard Quantum Portal Blocks are created & mined by [Quantum Portal Miners](quantum-portal-miner-qpm.md) using on-chain data provided by the [Quantum Portal Smart Contract (QPSC)](quantum-portal-smart-contracts-qpsc.md) on the `sourceChain` they are configured to mine transactions.

A standardQPB is made up of a pair of networks i.e. each block requires a source and destination network. The block numbers for standardQPBs are incremented independently on each network.&#x20;

For example, when a QPM is configured to mine Ethereum `sourceChain` transactions, both of the following conditions can be true:

1. A transaction with the `sourceChain` of Ethereum and `destinationChain` of BSC;\
   ETH <--> BSC can have minedStandardQPB #1 (ETH<-->BSC).&#x20;
2. Another transaction with the `sourceChain` of Ethereum and `destinationChain` of Polygon;\
   ETH <--> Polygon can have minedStandardQPB #1 (ETH<-->Polygon) as well.

These numbers are incremented independently as minedStandardQPBs are chain-specific, not chain-agnostic.

## Finalized Quantum Portal Blocks (finalizedQPB)

There is a concept of finalized blocks for Quantum Portal. This concept treats Standard Blocks the same way as transactions. Where a pool of Standard Blocks is mined but not finalized yet. After certain criteria are met, then this pool of blocks is finalized and assigned a Finalized Block Number.

Finalized Quantum Portal Blocks are created & finalized by [Quantum Portal Validators](quantum-portal-validator-qpv.md) using verification threshold signatures [Quantum Portal Miners](quantum-portal-miner-qpm.md) for minedStandardQPBs in the mempool and verified against on-chain data. Quantum Portal Validators are chain agnostic and can finalize minedQPBs for any integrated chain.

A finalizedQPB is also made up of a pair of networks i.e. each block requires a source and destination network. Similar to minedStandardQPBs, the block numbers for finalizedQPBs are also incremented independently on each network.&#x20;

For example, when a QPV finalizes minedStandardQPBs both of the following conditions can be true:

1. A minedStandardQPB with the `sourceChain` of Ethereum and `destinationChain` of BSC;\
   ETH <--> BSC with a minedStandardQPB #1 (ETH<-->BSC) can have finalizedQPB #1 (ETH<-->BSC).
2. Another minedStandardQPB with the `sourceChain` of Ethereum and `destinationChain` of Polygon;\
   ETH <--> Polygon with minedStandardQPB #1 (ETH<-->Polygon) can have finalizedQPB #1 (ETH<-->Polygon) as well.

finalizedQPB numbers are incremented independently as finalizedQPBs are chain-specific, not chain-agnostic, similar to minedStandardQPBs.
