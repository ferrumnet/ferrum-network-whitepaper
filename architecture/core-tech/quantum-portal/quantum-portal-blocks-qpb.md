# 🧱 Quantum Portal Blocks (QPB)

There are two types of Quantum Portal Blocks.&#x20;

1. Mined Blocks
2. Finalized Blocks

## Mined Quantum Portal Blocks (minedQPB)

Mined Quantum Portal Blocks are created & mined by [Quantum Portal Miners](quantum-portal-miner-qpm.md) using on-chain data provided by the [Quantum Portal Smart Contract (QPSC)](quantum-portal-smart-contracts-qpsc.md) on the `sourceChain` they are configured to mine transactions.

A minedQPB is made up of a pair of networks i.e. each block requires a source and destination network. The block numbers for minedQPBs are incremented independently on each network.&#x20;

For example, when a QPM is configured to mine Ethereum `sourceChain` transactions, both of the following conditions can be true:

1. A transaction with the `sourceChain` of Ethereum and `destinationChain` of BSC;\
   ETH <--> BSC can have minedQPB #1 (ETH<-->BSC).&#x20;
2. Another transaction with the `sourceChain` of Ethereum and `destinationChain` of Polygon;\
   ETH <--> Polygon can have minedQPB #1 (ETH<-->Polygon) as well.

These numbers are incremented independently as minedQPBs are chain-specific, not chain-agnostic.

## Finalized Quantum Portal Blocks (finalizedQPB)

Finalized Quantum Portal Blocks are created & finalized by [Quantum Portal Validators](quantum-portal-validator-qpv.md) using verification threshold signatures [Quantum Portal Miners](quantum-portal-miner-qpm.md) for minedQPBs in the mempool and verified against on-chain data. Quantum Portal Validators are chain agnostic and can finalize minedQPBs for any integrated chain.

A finalizedQPB is also made up of a pair of networks i.e. each block requires a source and destination network. Similar to minedQPBs, the block numbers for finalizedQPBs are also incremented independently on each network.&#x20;

For example, when a QPV finalizes minedQPBs both of the following conditions can be true:

1. A minedQPB with the `sourceChain` of Ethereum and `destinationChain` of BSC;\
   ETH <--> BSC with a minedQPB #1 (ETH<-->BSC) can have finalizedQPB #1 (ETH<-->BSC).
2. Another minedQPB with the `sourceChain` of Ethereum and `destinationChain` of Polygon;\
   ETH <--> Polygon with minedQPB #1 (ETH<-->Polygon) can have finalizedQPB #1 (ETH<-->Polygon) as well.

finalizedQPB numbers are incremented independently as finalizedQPBs are chain-specific, not chain-agnostic, similar to minedQPBs.
