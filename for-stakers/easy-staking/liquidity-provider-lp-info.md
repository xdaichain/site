# Liquidity Provider \(LP\) Info

In addition to [rewards provided by Uniswap for participation](https://uniswap.org/docs/v2/advanced-topics/understanding-returns/), **ETH/STAKE liquidity providers receive rewards from EasyStaking**. The distribution contract accumulates STAKE when stakers exit the protocol. Funds are added based on a simple formula: `15 - staker's earned APR`. In addition, the contract receives fees assessed \(2%\) when a staker exits with an instant withdrawal. For examples, see the [EasyStaking page](./).  
  
**A script runs on average every 5-9 days and provides rewards to the top 100 LP providers**, based on how much STAKE they have placed in the pool. 

{% hint style="warning" %}
Participating as an LP carries certain risks, such as the risk of impermanent \(or divergence\) loss where prices in the pool diverge from external market prices. [More info on impermanent/divergence loss.](https://medium.com/@pintail/uniswap-a-good-deal-for-liquidity-providers-104c0b6816f2)
{% endhint %}

## LP Resources

* Uniswap ETH/STAKE Pool: [https://uniswap.info/pair/0x3B3d4EeFDc603b232907a7f3d0Ed1Eea5C62b5f7](https://uniswap.info/pair/0x3B3d4EeFDc603b232907a7f3d0Ed1Eea5C62b5f7) 
* LP Distributions Tracker: [https://stake-reward-distribution.xdaichain.com/](https://stake-reward-distribution.xdaichain.com/)

| Round | Date | Details |
| :--- | :--- | :--- |
| 1 | 2.9.2020 | 🎉 Initial distribution was successfully distributed to all 119 providers. |
| 2 | 14.9.2020 | Distribution to top 100 providers. Round 2 distribution slightly delayed due to EasyStaking update. LP distribution includes LPs participating in [https://sakeswap.finance/\#/swaps/eth\_stake](https://sakeswap.finance/#/swaps/eth_stake)  |

* LP Distribution Contract: [https://etherscan.io/address/0x34fcb7f4edfd95761e6cbcf0fa34d19afd13089d](https://etherscan.io/address/0x34fcb7f4edfd95761e6cbcf0fa34d19afd13089d) 
* LP Governance: Coming Soon 
* Sakeswap.finance: It is possible to leverage your Uniswap position by [depositing your STAKE-ETH UNI-V2 ](https://sakeswap.finance/#/swaps/eth_stake%20)and earning SAKE in addition to your LP rewards. Just as with any external protocols, do your research and use at your own risk!

## Adding to the Liquidity Pool

For now there is a single liquidity pool with Uniswap. More pools may be added in the future. You can use [Zapper.fi](../tools-supporting-stake/zapper.md) to stake, or add with Uniswap:

1\) Go to [https://uniswap.info/pair/0x3B3d4EeFDc603b232907a7f3d0Ed1Eea5C62b5f7](https://uniswap.info/pair/0x3B3d4EeFDc603b232907a7f3d0Ed1Eea5C62b5f7) and click Add Liquidity

![](../../.gitbook/assets/liquidity-1.png)

2\) Connect to your wallet of choice on the Ethereum Network.

![](../../.gitbook/assets/lp2.png)

3\) Enter in the amount of STAKE or ETH you would like to supply. The corresponding token value will fill automatically. This is a 50/50 pool.

![](../../.gitbook/assets/lp3.png)

4\) You will see the amount of tokens you receive for providing liquidity. Click Confirm to proceed.

![](../../.gitbook/assets/lp4.png)

5\) Continue with your wallet to pay gas fees and confirm the transaction.

![](../../.gitbook/assets/lp5.png)

6\) Once complete, you will see your pool share and the UNI-V2 tokens in your Ethereum wallet.

![](../../.gitbook/assets/lp6.png)

7\) To exit a pool, click on the pool and approve the transaction, then choose the percentage to remove.

![](../../.gitbook/assets/lp7.png)

![](../../.gitbook/assets/lp7-2.png)

## Receiving Rewards

Rewards are automatically distributed to your account when the script runs if you are in the top 100 providers. The script runs every 5-9 days.   
  
Once a distribution occurs, simply go to your wallet and check your updated STAKE balance. If you need to add STAKE to your wallet, you can Search and Add, or enter in the STAKE contract: [0x0ae055097c6d159879521c384f1d2123d1f195e6](https://etherscan.io/token/0x0ae055097c6d159879521c384f1d2123d1f195e6)

Check past distributions with the distribution tracking tool: [https://stake-reward-distribution.xdaichain.com/](https://stake-reward-distribution.xdaichain.com/) 

You can check the current value of the LP contract at [https://etherscan.io/address/0x34fcb7f4edfd95761e6cbcf0fa34d19afd13089d](https://etherscan.io/address/0x34fcb7f4edfd95761e6cbcf0fa34d19afd13089d)

## STAKE LP Distribution Script

Distributions to LP participants occur once every 7 days on average at a random interval. This prevents any user from entering the liquidity pool at a predetermined time to receive STAKE distributions then exiting shortly thereafter.

The top 100 providers receive rewards based on the percentage of STAKE they have in the pool.

The distribution script runs on a centralized server, and its results can be checked for bias or inaccuracy by any interested party. A multi-signature wallet controls EasyStaking parameters, including the address which calls distributions. If issues arise, this address may be changed through the multi-sig process.

Easy staking is non-custodial, no funds are collected and 100% of accumulated rewards are distributed to Easy Staking participants and LP participants.

More liquidity pools with different asset bases may be added in the future, and the distribution mechanics for these pools will be explored further.

## LP Governance

There are a number of parameters for liquidity pool distributions that will be decided in the future by TBD governance mechanisms. This includes additional pools to add \(like Mooniswap\), how many participants receive distributions and other factors.

Voting power will be influenced by the amount of STAKE/ETH an individual has committed to the pool. Details are in process.

