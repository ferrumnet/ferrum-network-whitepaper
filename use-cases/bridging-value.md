# Bridging Value

Quantum Portal and MultiChain Tokens provide a way to update the supply of tokens across multiple chains without using bridges. This is done by creating a master contract that stores the total supply and balances of tokens across all chains. When a user makes a transfer on one chain, the transfer is recorded in the master contract, which then updates the balances and total supply on all chains.

To accomplish this, the master contract should be deployed on each chain and connected through Quantum Portal. The MultiChain Tokens smart contract should also be deployed on each chain and connected to the master contract.

When a user makes a transfer on one chain, the MultiChain Tokens contract on that chain will first transfer the tokens to the recipient and then notify the master contract of the transfer. The master contract will then update the balances and total supply on all chains by calling the corresponding functions on the MultiChain Tokens contracts.

For example, let's say a user on Ethereum wants to transfer 10 tokens to a user on BSC. The user would initiate the transfer on Ethereum by calling the transfer function on the MultiChain Tokens contract on Ethereum. This contract would then transfer the tokens to the recipient and call the notifyTransfer function on the master contract through Quantum Portal.

The master contract would then update the balances and total supply on both Ethereum and BSC by calling the corresponding functions on the MultiChain Tokens contract on each chain.

This approach allows for seamless cross-chain transfers without the need for bridges. Additionally, it enables users to participate in staking and other DeFi activities across multiple chains while maintaining the same token balances and supply across all chains.
