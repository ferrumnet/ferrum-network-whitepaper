# ⚖ Value-Constrained PoS Rollup (VCPR)

## Overview

Value-Constrained PoS Rollups are invented by the founder of Ferrum Network. Much like Optimistic and ZK Rollups, value-constrained PoS Rollups use the security of the underlying chains. The value constraints are enforced by the L1 chain. (e.g. Ethereum)

The value is received from the L1 chain oracles (e.g. Uniswap on-chain pricing oracle).

## Current Approaches for Securing Rollups

1. Optimistic Rollup
2. PoS Rollup
3. ZK Rollup

### Optimistic Rollup

Cryptographically secure but complicated in practice.

### PoS Rollup

Secured by the roll-up validators, hence significantly less secure than the base network

### ZK Rollup

ZK Rollups are cryptographically secure. Currently, it's hard to get them to work with smart contracts, as the proof for the whole loop of value must be created and submitted to the base chain. However, providers like ZK, Polygon, and others have made some progress in this area.&#x20;

## Why not use ZK or Optimistic Rollups?

We are building MultiChain Rollup. We need to keep rollup tech independent from the L1 implementation details and support EVM, non-EVM, as well as DotSama chains.

We need the full support of smart contracts on each integrated network.

Validity proofs (like Optimistic or ZK Rollups) can be added in the future as an add-on. Hence, once Optimistic or ZK Rollup tech is matured, we can quickly adopt it to make our rollup more secure for integrated networks. We are also working on the possibility of integrating either ZK or Optimistic Rollups within the VCPR procedure.&#x20;

## Why not use simple PoS Rollups?

For simple PoS Rollups, the value controlled can be larger than the value staked, which presents malicious behavior-based attack vectors. For example, one PoS Rollup block may have $10M in value, while a validating staker has only $10k staked. This process relies on the Rollups relay chain or off-chain worker security and cannot tap into the base layer chain security.

## How does Value-Constrained PoS Rollup (VCPR) work?

In Value-Constrained PoS Rollups, blocks are finalized as long as the sum of value transferred out from the source chain is less than the sum of stakes used to validate them.

For example, A block transfers out 2,000 USDT and is validated by a validator with a staked value of 10k. This block can be finalized. However, if a block transfers 2,000,000 USDT out from the source chain, it will only be finalized after enough validators have validated the blocks such that their staked sum value is more than 2,000,000. This value-constrained limitation ensures validators always have more value staked than the amount being validated. As discussed earlier, The value constraints are enforced by the underlying L1 chain, and the value is also received from the L1 chain oracles, eliminating reliance and the need for trust on the Rollups off-chain worker or relay infrastructure.



