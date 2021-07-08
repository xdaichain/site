---
description: High APR stablecoin pools on xDai
---

# Curve Finance

Curve gives users & protocols the ability to exchange stablecoins with low fees and low slippage. Users can also provide liquidity and receive high-APR rewards for providing liquidity to the protocol.  Curve is a major protocol in the DeFi space, and we are excited to welcome them to the xDai stable ecosystem!

* **Curve on xDai**: [https://xdai.curve.fi](https://xdai.curve.fi/pools)
* **Curve Announcement**: [https://curve.substack.com/p/july-1-2021-the-xdai-is-cast-](https://curve.substack.com/p/july-1-2021-the-xdai-is-cast-)
* **Learn About Curve:** [https://resources.curve.fi/](https://resources.curve.fi/)

![](../../.gitbook/assets/curve-on-xdai.png)

## Curve Basics

{% hint style="info" %}
See the [Curve docs](https://resources.curve.fi/) for basics on exchanging stable coins and depositing / withdrawing liquidity from the protocol.
{% endhint %}

## Connect with MetaMask

1\) If you haven't added the xDai chain to MetaMask, [follow these instructions](../../for-users/wallets/metamask/metamask-setup.md) to setup and switch to the xDai Network.

2\) You will need a little xDai to pay for transactions. You [can get some automatically by bridging assets to xDai, from the xDai faucet, purchase with fiat or in other ways](../../for-users/getting-started-with-xdai.md#2-get-a-little-xdai).

3\) Go to the Curve site at [https://xdai.curve.fi](https://xdai.curve.fi/pools). Click **Connect Wallet** and confirm the xDai address in MetaMask you want to use with Curve. 

![Connect your xDai address to Curve](../../.gitbook/assets/curve-connect-wallet.png)

## Swap using Curve Pools

From the homepage, you will see the option to swap using existing pools.

![](../../.gitbook/assets/existing-pools-1.png)

**1\) Select the following**_**:**_

1. The coin you want to swap from.
2. The amount to swap.
3.  The asset you wish to receive. The amount will autopopulate, along with the exchange rate/fees and pool the trade will be routed through.

{% hint style="info" %}
Note, for **DAI you will need to use wrapped xDai**, not standard xDai. The easiest way to convert Dai to wxDai is with [wrapeth](https://wrapeth.com/).  
[_Additional info about wrapped xDai_](../../for-developers/developer-resources/wrapped-xdai.md)_._ 
{% endhint %}

![](../../.gitbook/assets/swapping.png)

2\) Click **Sell** to process. You will sign 2 transactions in MetaMask. The first to approve the contract, and the second to pay for the transaction.  You can adjust the gas price based on the [BlockScout Gas Tracker](https://blockscout.com/poa/xdai).

![Transaction 1 Click Sell \| Confirm Contract](../../.gitbook/assets/tx-1.png)

![Transaction 2 Adjust Gas Price \| Confirm Transaction](../../.gitbook/assets/tx-2.png)

![Gas Tracker on BlockScout. Click \(i\) to expand](../../.gitbook/assets/gas-tracker.png)

3\) Find the transaction in MetaMask under the Activity Tab. Click icon in details to View the tx in BlockScout.

![](../../.gitbook/assets/view%20%281%29.png)

## Funding a Pool

Basic instructions below. For more information see the [Curve docs](https://resources.curve.fi/). 

1\) Click on the pool you want to deposit to. 

![](../../.gitbook/assets/curve-1.png)

2\) Select Deposit from the menu.

![](../../.gitbook/assets/curve-2.png)

3\) Input funding amounts.

1. You can fund with a single token or multiples. If there is a lower amount of a certain token, providing additional amounts of that token will increase your rewards.
2. Check or uncheck these boxes to add a balanced proportion of tokens or to add the max amount in your connected wallet.
3. Click to either deposit and receive x3CRV tokens \(for this pool example\) to your wallet, or Deposit and stake in gauge to stake and earn additional rewards on your CRV tokens.

![](../../.gitbook/assets/curve-3.png)

4\) Click Deposit/Deposit & stake in gauge and confirm in MM to approve the Curve contract.

![](../../.gitbook/assets/curve-4.png)

5\) Confirm the second transaction to process the deposit. Adjust gas price if desired \(typically 1 Gwei, in times of high usage check prices on [BlockScout](https://blockscout.com/poa/xdai)\)

![](../../.gitbook/assets/curve5.png)

6\) If you chose to Deposit and stake in gauge, you will sign a second contract approval to allow Curve to send x3CRV to the staking contract.

![](../../.gitbook/assets/curve-6.png)

7\) Confirm the 2nd transaction to start staking in gauge.

![](../../.gitbook/assets/curve-7.png)

8\) Once confirmed you can see the amount staked. Click on a transaction to view in BlockScout.

![](../../.gitbook/assets/curve-8.png)

![BlockScout txs showing mint and transfer of x3CRV to staking gauge](../../.gitbook/assets/curve-9.png)

9\) If you chose to simply deposit your tokens to your wallet, or unstake from the application, you can easily add the x3CRV token to MetaMask using BlockScout.

Find a transaction or go to the token for the pool you have funded. In the example above the token address is [0x1337BedC9D22ecbe766dF105c9623922A27963EC](https://blockscout.com/xdai/mainnet/tokens/0x1337BedC9D22ecbe766dF105c9623922A27963EC/token-transfers)

1. Click on the fox icon next to the address.
2. Add to your MetaMask wallet.

![](../../.gitbook/assets/curve-10.png)





