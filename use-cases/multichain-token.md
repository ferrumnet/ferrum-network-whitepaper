# Multichain Token

Ferrum Network's Quantum Portal Nodes and Quantum Portal Smart Contracts can be used to launch a multichain token with supply on multiple networks such as Ethereum, BSC, and other EVM networks. Additionally, non-EVM networks such as Algorand can be added. The supply of the token can be managed across networks without the need to utilize a bridge.

Here is an example of a MultiChain token:

```solidity
// SPDX-License-Identifier: MIT

pragma solidity ^0.8.0;
import "./MultiChainBase.sol";
import "foundry-contracts/contracts/token/ERC20/ERC20.sol";

contract MitlChainToken2Master is ERC20, MultiChainMasterBase {
    uint256 public TOTAL_SUPPLY = 100000 * 10**18;

    constructor() {
    }

    function initialMint() external onlyOwner {
        require(totalSupply == 0, "Already initialized");
        _mint(msg.sender, TOTAL_SUPPLY);
    }

    /**
     @notice Mints and burns.
       Note: This is not secure, becuase there is no guarantee that the burn part on a remote chain
       will go through. This is for demonstration purpose.
       TODO: Implement a two-phase commmit approach to ensure mint and burn happen atomically.
     */
    function mintAndBurn(uint64 mintChain, uint64 burnChain, uint amount, uint mintFee, uint burnFee) external {
        // Pay FRM fee. TODO: Implement
        // IQuantumPortalFeeManager feeManager = IQuantumPortalFeeManager(portal.feeManager());
        // IERC20(feeManager.feeToken()).transferFrom(msg.sender, address(feeManager), mintFee + burnFee);
        // feeManager.depositFee(address(this));

        if (mintChain == CHAIN_ID) {
            _mint(msg.sender, amount);
        } else {
            address remoteContract = remoteAddress(mintChain);
            bytes memory method = abi.encodeWithSelector(MitlChainToken2Client.mint.selector, msg.sender, amount);
            portal.run(mintFee, mintChain, remoteContract, msg.sender, method); // The fee is base fee charged on this side. Covers enough to fail the tx on the other side.
        }
        if (burnChain == CHAIN_ID) {
            _burn(msg.sender, amount);
        } else {
            address remoteContract = remoteAddress(burnChain);
            bytes memory method = abi.encodeWithSelector(MitlChainToken2Client.burn.selector, msg.sender, amount);
            portal.run(burnFee, burnChain, remoteContract, msg.sender, method);
        }
    }

    function remoteAddress(uint256 chainId) public view returns(address rv) {
        rv = remotes[chainId];
        rv = rv == address(0) ? address(this) : rv;
    }
}

contract MitlChainToken2Client is ERC20, MultiChainClientBase {

    /**
     @notice We make sure this is only calle as part of a quantum portal transaction.
      As an extra security measure, you can pass in a signed message by the owner.
     */
    function mint(address to, uint amount) external {
        (uint netId, address sourceMsgSender,) = portal.msgSender();
        require(netId == MASTER_CHAIN_ID && sourceMsgSender == masterContract, "Not allowed");
        _mint(to, amount);
    }

    /**
     @notice We make sure this is only calle as part of a quantum portal transaction.
      As an extra security measure, you can pass in a signed message by the owner.
     */
    function burn(address from, uint amount) external {
        (uint netId, address sourceMsgSender,) = portal.msgSender();
        require(netId == MASTER_CHAIN_ID && sourceMsgSender == masterContract, "Not allowed");
        _burn(from, amount);
    }

}
```

Here's a description of each function in the code template provided for a multi-chain token:

* `MitlChainToken2Master` contract: This contract is the main smart contract that manages the token's supply and the interaction with the Quantum Portal. Here are the functions included:
  * `constructor`: This is a constructor function that sets up the initial state of the contract.
  * `initialMint`: This is a function that allows the contract owner to initialize the token's supply by minting the total supply and assigning it to themselves.
  *   `mintAndBurn`: This is a function that allows users to mint and burn tokens across different chains. The function takes four arguments:

      * `mintChain`: The ID of the chain on which the user wants to mint new tokens.
      * `burnChain`: The ID of the chain on which the user wants to burn tokens.
      * `amount`: The number of tokens to mint and burn.
      * `mintFee`: The fee in FRM tokens to be paid for the mint transaction.
      * `burnFee`: The fee in FRM tokens to be paid for the burn transaction.

      The function first checks if the mint and burn chains are the same as the master chain (where the contract is deployed). If they are, the mint and burn functions are called directly. Otherwise, the function creates a `bytes` representation of the `mint` or `burn` function call on the `MitlChainToken2Client` contract, which is then executed on the remote chain using the Quantum Portal's `run` function.
  * `remoteAddress`: This is a helper function that returns the remote address of the contract on the specified chain.
* `MitlChainToken2Client` contract: This contract is deployed on each of the remote chains and is used to receive and execute the `mint` and `burn` functions that were called on the master chain. Here are the functions included:
  * `mint`: This function is called by the Quantum Portal when a user wants to mint new tokens on the remote chain. The function checks that the call was made by the master chain, and then mints the specified number of tokens to the user's address.
  * `burn`: This function is called by the Quantum Portal when a user wants to burn tokens on the remote chain. The function checks that the call was made by the master chain, and then burns the specified number of tokens from the user's address.
