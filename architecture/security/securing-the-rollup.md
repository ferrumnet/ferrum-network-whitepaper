# Securing the Rollup

The Ferrum network uses an innovative concept called Value Constrained POS Rollup (VCPR). Value-Constrained PoS Rollups were invented by [Naiem Yeganeh](https://www.linkedin.com/in/naiem-yeganeh-12874712), the founder of Ferrum Network. Much like Optimistic and ZK Rollups, value-constrained PoS Rollups use the security of the underlying chains. The value constraints are enforced by the L1 chain. (e.g. Ferrum Network).

\
The current approaches to securing rollup include ZK, Optimistic and simple POS. Each of these approaches has its own drawbacks. Ferrum Network uses VCPR because we are building a [Multichain Rollup](../core-tech/value-constrained-pos-rollup-vcpr.md). To support EVM, non-EVM, and DotSama chains, we need to keep rollup tech independent from the L1 implementation details. We need the full support of smart contracts on each integrated network. For simple PoS Rollups, the value controlled can be larger than the value staked, which presents malicious behavior-based attack vectors. For example, one PoS Rollup block may have $10M in value, while a validating staker has only $10k staked. This process relies on the Rollups relay chain or off-chain worker security and cannot tap into the base layer chain security.

## How does Value-Constrained PoS Rollup (VCPR) secure the network?

In Value-Constrained PoS Rollups, blocks are finalized as long as the sum of the value transferred away from the source chain is less than the sum of the value staked used to validate the block.

This means that any action can be executed on the rollup chain as long as the combined value of these transactions does not exceed the staked amount for the rollup. This helps ensure the economic security of the rollup and enables the building of fully functional and secure rollups on the Ferrum Network.

\
