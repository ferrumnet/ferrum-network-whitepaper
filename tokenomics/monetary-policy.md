# Monetary Policy

## Ferrum’s Monetary Policy

A network’s monetary policy is one of the biggest differentiating factors when it comes to tokenomics that are designed for networks. In order for a network to gain adoption, there needs to be a large enough incentive for early adopters.&#x20;

### **Expansion Periods**

An expansion period is the amount of time that elapses between the times in which tokens are released from the reserves. You can also think of the reserves as the uncirculated supply. An expansion period will have a duration of 7 days. FRM reserves will have a half life of just under 4.5 years. That means that every 4.5 years, the remaining supply of the reserves will be cut in half. This approach accomplishes something akin to Bitcoin’s halvening only through PoS mechanisms.

For example, let's say that 250,000,000 tokens are in the reserve after the Merge takes place. If every expansion period, a total of 0.3% of those tokens are released, that means that the supply of the reserves will reach 125,000,000 in 4.5 years.

We have put a tremendous amount of thought into this to ensure a few things:

* How Quantum Portal Miners (QPMs) and Quantum Portal Validators (QPVs) will be rewarded for ensuring the security, efficiency and overall effectiveness of the network
* QPMs and QPVs will be incentivized to grow their stake in the network
* How the Treasury can stay funded to ensure that operations can continue and both builders and users can be incentivized
* How the distribution of these tokens for the aforementioned items can sustain equilibrium as it pertains to emissions

### Rewarding QPMs and QPVs

If you remember earlier on in the article we discussed how the folks ensuring the security of a network need to have an incentive. Early on in a network’s existence, transaction fees alone will not suffice as a rewards mechanism since transactions may be few and far between. With our reserves having a half life similar to that of Bitcoin, we believe that there will be enough of an incentive to reward early adopters of the network.

#### **Incentivize QPMs and QPVs to Grow their Stake**

One interesting note here is that block rewards generated each expansion period will be distributed to QPMs and QPVs as cFRM. This means that QPMs and QPVs will be less inclined to sell their rewards as they would incur a fee. We will in fact however, be removing the unwrapping fee if they so choose to opt for our autocompounding feature that allows them to restake their rewards on the network.&#x20;

_Note: This means that at the very least, 2% of the uncirculated supply will automatically be distributed to cFRM stakers as each time block rewards are distributed, tokens from that expansion period will be subjected to the 2% transfer fee. This will also add to Ferrum’s goals of maintaining a deflationary token economy as each time cFRM is transacted, tokens are burned._

### Funding the Treasury

Up until now, Ferrum has taken a product oriented approach to the way we ran the business. Now, as we pivot, we need to take a network oriented approach to how the network runs itself. A million dollars a year in revenue from a suite of Blockchain as a Service products simply will not cut it when it comes to maintaining a network and incentivizing behavior on a network.

Therefore, we have decided that 20% of tokens released every expansion period will be allocated to the Treasury. As stated previously, Treasury tokens will be used to support categories such as Exchange Liquidity & Market Making, Bridge Liquidity, Ecosystem, and Mainnet and Parachain Fund.

### Emissions Breakdown

According to[ this article from September 2020](https://medium.com/ferrumnetwork/year-two-token-emission-schedule-5b961d89f0bb), year 1 for Ferrum had the largest emission rate at 41.9%. This was primarily due to the vesting for the private and public sales. Year 2 saw a drastically reduced emission rate of 7.45%. Since then, the emissions rate for years 3 and 4 of 7.45% has stayed consistent.

We will start measuring yearly emissions from the moment the Merge is complete. Due to the necessity to boost the engagement on the soon-to-be newly launched network, there will be a slight uptick in emissions during the first year of the network’s lifespan.&#x20;

We will know more regarding exactly how many tokens will be left in the reserve after the Merge is complete, but lets assume there is 40% of the max supply left in reserve post-Merge. If we release 0.3% of that supply every 4 days, we will will have a year 1 emissions rate of around 10%. This yearly rate of emissions will reduce itself as the supply of the reserve fades.&#x20;

### Transaction Fees

Choosing how much transaction fees are to cost is another important consideration for any network. Transaction fees are mostly meant to cover the processing and long term storage cost of transactions. So there are a few items to consider when determining how to charge transaction fees.

1. The size of the transaction. The larger the transaction, the more resources are needed to store and process it.
2. A minimum payable fee. This fee needs to exist regardless of the size of the transaction. This is meant to prevent DDoS attacks by making such attacks prohibitively expensive and eliminating the possibility of an attacker generating millions of small transactions to flood and crash the system.

The parameters set in response to these items will ultimately be contingent on criteria such as current transaction volumes, hardware prices, and FRM valuation and should be subject to alteration by way of approving referenda via governance as a means of adapting to changes in the above criteria.

To calculate the fees generated in one year:

* We have a fixed transaction fee of 0.1 FRM for each transaction.
* We have 100,000 transactions per day initially.
* The transaction volume is increasing at a rate of 20% per month.

To calculate the number of transactions in one year, we need to multiply the initial transaction volume by the number of days in a year:

```sql
Number of transactions in one year = 100,000 * 365 = 36,500,000
```

To calculate the fees generated in one year, we need to multiply the number of transactions in one year by the transaction fee:

```sql
Fees generated in one year = 36,500,000 * 0.01 = 3,650,000 FRM
```

However, the transaction volume is increasing at a rate of 20% per month. To account for this, we need to calculate the transaction volume for each month and then sum up the fees generated for each month. Here's the formula to calculate the transaction volume for each month:

```csharp
Transaction volume = 100,000 * (1 + 0.2)^n, where n is the number of months
```

To calculate the fees generated for each month, we need to multiply the transaction volume for that month by the transaction fee:

```sql
Fees generated for each month = Transaction volume * 0.1
```

We can then sum up the fees generated for each month to get the total fees generated in one year:

```sql
Total fees generated in one year = Fees generated for each month in month 1 + Fees generated for each month in month 2 + ... + Fees generated for each month in month 12
```

#### **How will Transaction Fees support QPMs, QPVs and the Treasury?**

Transaction fees are also one of the mechanisms used to reward QPMs and QPVs as well as fund the Treasury. At the end of every expansion period 5% of the transaction fees generated on the network during said period will be burned. The rest will be distributed to a virtual pool along with the 0.3% of reserves. This pool will then be distributed with 80% going to QPMs and QPVs and the other 20% going to the Treasury.

### Token Burns

FRM became a deflationary asset as part of the creation of the Ferrum Cross-Chain Token Bridge, which is of course evolving into our multi-chain swapping protocol, MultiSwap. We furthered this agenda with the advent of our latest DeFi 2.0 product, Crucible, which burns between 0.1–0.4% of all transacted volume of the wrapped reflection version of FRM, cFRM.

Not only does burning FRM make the asset more scarce, it also helps to combat emissions. At the time of writing a total of (INSERT NUMBER) FRM and counting, have been burned. These tokens have been effectively removed from the Total Supply!&#x20;

It has long been the goal of the team to make FRM deflationary by way of the network as well. While assets like BTC are deflationary in nature by way the Halvening, so will be FRM by way of our monetary expansion mechanism. As each year passes, the amount of FRM will be less and less. However, we wanted to take it one step further and introduce regular burns through two other mechanisms:

1. Through transaction fees on the network
2. By using cFRM as the token through which monetary expansion takes place.
