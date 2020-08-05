---
description: Basic Instructions
---

# Instructions

{% hint style="success" %}
Easy Staking is now available for stakers at [https://easy-staking.xdaichain.com/](https://easy-staking.xdaichain.com/)
{% endhint %}

To begin, enable your web3wallet \(such as [MetaMask](https://metamask.io/) or [NiftyWallet](https://chrome.google.com/webstore/detail/nifty-wallet/jbdaocneiiinmjbjlgalhcelgbejmnid)\) with an address that contains both ETH \(for gas fees\) and STAKE \(for staking\). If you've sent STAKE to your wallet address but it is not showing up, [add STAKE as a custom token](../stake-token/get-stake/add-stake-to-metamask.md). Then connect your wallet to the application.

![](../../.gitbook/assets/easy-staking-1.png)

## Make A Deposit / Multi-Deposits

Check estimated emissions with the UI calculator and make a deposit from the deposit screen.  Easy Staking has a multi-deposit feature where you can make as many deposits as you like and each one accrues interest based on the staking time. 

{% embed url="https://youtu.be/8K8i2zCvkLk" %}

## Initiate a Withdrawal

Access withdrawals by clicking on details for any deposit. 

![](../../.gitbook/assets/deets-1.png)

There are two types of withdrawals - Instant and Scheduled. Select the type you would like and confirm in your web3 wallet.

1. A **scheduled withdrawal** is processed in 2 transactions. With the first transaction, you schedule the withdrawal. It will be available to withdraw after 12 hours, and for a limited 12 hour time frame once it is available. Scheduled withdrawals do not incur a % fee \(but gas fees are assessed for both transactions\). More details are available here
2. An **instant withdrawal** is processed immediately and you are assessed a small fee \(2%\) to withdraw.

![](../../.gitbook/assets/deets2.png)

_&lt;video for withdrawal in process&gt;_

## Staking from a wallet without the UI

You can transact with the EasyStaking proxy contract directly by sending STAKE to `0xecbCd6D7264e3c9eAc24C7130Ed3cd2B38F5A7AD`  . Once your transaction is approved, you can connect your wallet to the Easy Staking UI to view staking details.

_Note: Only send STAKE tokens to this address_

## Liquidity Providers

If you are interested in supplying Liquidity in the form of STAKE / ETH and earning staking rewards as an LP, you can add liquidity to the Uniswap pool here: [https://uniswap.info/pair/0x3B3d4EeFDc603b232907a7f3d0Ed1Eea5C62b5f7](https://uniswap.info/pair/0x3B3d4EeFDc603b232907a7f3d0Ed1Eea5C62b5f7)

More details about liquidity provider rewards are available on the [EasyStaking page](./#liquidity-pool-lp-participants). 

{% hint style="warning" %}
Instructions are in process for additional functionality such as using a Gnosis Multi-sig wallet. For more details about Easy Staking, please see the [EasyStaking page](./) and the [Parameters page](easy-staking-parameters.md).
{% endhint %}

