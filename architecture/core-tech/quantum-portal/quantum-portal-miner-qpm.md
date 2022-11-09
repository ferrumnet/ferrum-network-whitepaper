# ⛏ Quantum Portal Miner (QPM)

## Quantum Portal Miner

1. Anyone can become a miner
2. Required to configure Ferrum Network node as QP Miner and stake at least 250,000 FRM (subject to change) on the `sourceChain`
3. Can mine blocks but cannot finalize them
4. To mine for multiple `sourceChains` a minimum stake will be required natively on each `sourceChain`
5. Last action (mining a block) locks stake for a month

## Who can become a Quantum Portal Miner?

Anyone can become a Quantum Portal Miner by configuring the Ferrum Network Node as a Quantum Portal Mining node which requires you to stake a minimum amount of tokens on the `sourceChain` you would like mine Quantum Portal transactions from.

## **What is Quantum Portal Mining?**

The QP Miners take turns based on an algorithm to create and relay these blocks from the `sourceChain` to the `destinationChain`. QP Miners do this by running the Ferrum Node as a QP Miner (QP Node). Once configured, this QP Node monitors the transactions on the network that they have set up to be miners and staked tokens on. The QP Node monitors transactions on the `sourceChain` and if new data is available, it creates a block every 15 seconds. After creating a block, the QP Node calls the `mineRemoteBlock` on the `destinationChain` in order to execute the transaction and mine the [QP Block](quantum-portal-blocks-qpb.md). It is considered a mined block after the transaction executes on the `destinationChain`

Once a transaction is mined, the record of a mined transaction is added to the `destinationChain`

{% hint style="info" %}
``[`Quantum Portal Blocks`](quantum-portal-blocks-qpb.md)`are made up of a pair i.e. sourceChain and destinationChain. The block numbers are incremented independtly for each pair. So an ETH <> BSC pair can have block #1 and ETH <> Polygon pair can also have block #1. Learn more on the` [`Quantum Portal Blocks`](quantum-portal-blocks-qpb.md) `page.`
{% endhint %}
