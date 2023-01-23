# 🔍 Quantum Portal Multichain Explorer (QPME)

The Quantum Portal Multichain Explorer (QPME) brings together information from [Quantum Portal Smart Contracts](quantum-portal-smart-contracts-qpsc.md) deployed on multiple chains and provides the ability to interact with these contracts through the Ferrum Virtual Machine (FVM) and its Quantum Portal Node infrastructure.&#x20;

## A Multichain Explorer - QPME

QPME is a Multichain explorer. This means it needs to display data for various chains, this data includes transactions, blocks, and QPME also needs to display the minedQPBs and finalizedQPBs for each chain.&#x20;

QPME is designed to help users easily search for transactions, addresses, blocks, tokens, and more with the following available search parameters.

Search by:

1. Tx ID
2. Address
3. standardQPB
4. finalizedQPB
5. Token Name & Symbol

Filter by:

1. Source Chain
2. Destination Chain
3. Date Time Range

QPME will also show a stats card showing important information, including:

1. FRM Price
2. Market Cap
3. Number of QP Transactions

Additional relevant information will include:

1. A list of the latest standardQPBs
2. A list of the latest finalizedQPBs
3. A list of the latest transactions

### Detailed Block View - standardQPB _(Standard Blocks)_

Block page (similar to etherscan, different fields). Block data can be read from the contract

1. Block Height (can iterate through blocks by clicking arrows like Etherscan)
   1. Quantum Portal Logo | Block Number (Quantum Portal)
2. Status:
   1. pending
   2. mined
   3. finalized
3. Finalized Block Number:
   1. pending
   2. 26 | Clickable
4. Timestamp:
   1. Quantum Portal Validation dateTime (Quantum Portal)
5. Transactions
   1. x transactions **| Clickable** in this block
6. Block Reward: x FRM

### Detailed Block View - Finalized _(Finalized Blocks)_

Block page (similar to etherscan, different fields). Block data can be read from the contract

1. Block Height (Finalized) (can iterate through blocks by clicking arrows like Etherscan)
   1. Quantum Portal Logo | Block Number (Quantum Portal)
2. Timestamp:
   1. Quantum Portal Validation dateTime (Quantum Portal)
3. _Standard Blocks_
   1. x blocks **| Clickable** in this _finalized block_
4. Finalized Block Reward: x FRM TODO (Discuss if this is required / feasible)
5. Accumulated Standard Block Reward: x FRM Shows the sum of the block reward for all standard blocks within this finalized block

### Detailed Transaction View

```javascript
struct QuantumPortalTransaction {
        uint64 timestamp;
        address remoteContract;
        address sourceMsgSender; 
        address sourceBeneficiary; // This can be set by the contract. Revert refunds will be made to this
        address token;
        uint256 amount;
        bytes method;
        uint256 gas; // provided gas in FRM
    }
```

1. Transaction Hash
   1. Quantum Portal Logo | Tx Hash (QP)
   2. Network Logo | Tx Hash (Source Chain) | Clickable
   3. Target Network Logo
2. Status
   1. Quantum Portal Logo | Status
      1. pending
      2. pending - mined
      3. success
      4. failed
   2. Network Logo | Status (Source Chain)
      1. Get the status from the network
3. Block
   1. Network Logo | Block Number (Source Chain) | Clickable
   2. Standard Block Number
      1. Quantum Portal Logo | Block Number | Clickable
   3. Finalized Block Number
      1. Quantum Portal Logo | Block Number | Clickable
4. Timestamp
   1. Network Logo | Timestamp (Source Chain)
   2. Quantum Portal
      1. mined | Timestamp
      2. finalized | Timestamp
5. From (sourceMsgSender) | Clickable
6. Interacted With (To) (remoteContract) | Clickable
7. Quantum Portal Contract (Source Chain) | Clickable
8. Tokens Transferred
   1. From
      1. Network Logo | Address (Source Chain) | Clickable
   2. To
      1. Network Logo | Address (Destination Chain) | Clickable
   3. For
      1. Amount | Token Logo | Token Name | (Token Symbol)
9. Transaction Fee
   1. FRM Fee
   2. Network Logo | Gas Fee (Source Chain)
10. Others
    1. Nonce
       1. Network Logo | Nonce
    2. Position
       1. Position in Standard Block
11. Input Data
    1. Show raw transaction data

### **Quantum Portal Transaction Lifecycle**

**State and Status Flow**

1. QP - Generated
   1. Source Network Transaction is Successful
   2. QP Status - pending
2. QP - Mined
   1. When a QP transaction that was pending is picked up by a QP Validator and mined in a standard block
      1. The standard block is added to the transaction detail view
   2. QP Status - pending - mined
3. QP - Finalized
   1. When a QP standard block is picked up by QP Validator and the standard blocks are finalized. A Finalized Block is generated and associated with all Standard Blocks in that pool.
      1. The finalized block is added to the transaction detail view
   2. QP Status
      1. failed
      2. success
