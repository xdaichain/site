---
description: Basic Instructions
---

# Instructions

{% hint style="success" %}
* Easy Staking is now available for stakers at [https://easy-staking.xdaichain.com/](https://easy-staking.xdaichain.com/)
* Launch details: [https://t.me/xdai\_official/160](https://t.me/xdai_official/160)
* Mobile ready to use use with [Alpha Wallet](https://alphawallet.com/), [Trust Wallet](https://trustwallet.com/), [Coinbase Wallet](https://www.coinbase.com/mobile), [Status](../../for-users/wallets/status-wallet.md), [Opera Browser](https://www.opera.com/crypto) and other Ethereum mobile wallets with browsing capabilities.
{% endhint %}

To begin, enable your web3wallet \(such as [MetaMask](https://metamask.io/) or [NiftyWallet](https://chrome.google.com/webstore/detail/nifty-wallet/jbdaocneiiinmjbjlgalhcelgbejmnid)\) with an address that contains both ETH \(for gas fees\) and STAKE \(for staking\). If you've sent STAKE to your wallet address but it is not showing up, [add STAKE as a custom token](../stake-token/get-stake/add-stake-to-metamask.md). Then connect your wallet to the application.

![](../../.gitbook/assets/easy-staking-1.png)

## Make A Deposit / Multi-Deposits

Check estimated emissions with the UI calculator and make a deposit from the deposit screen.  Easy Staking has a multi-deposit feature where you can make as many deposits as you like and each one accrues interest based on the staking time. 

{% embed url="https://youtu.be/8K8i2zCvkLk" %}

## Initiate a Withdrawal

{% embed url="https://youtu.be/B4tEyNlqLLE" %}

### Withdrawal Screenshots

Access withdrawals by clicking on details for any deposit. 

![](../../.gitbook/assets/deets-1.png)

There are two types of withdrawals - Instant and Scheduled. Select the type you would like and confirm in your web3 wallet.

1. A **scheduled withdrawal** is processed in 2 transactions. With the first transaction, you schedule the withdrawal. It will be available to withdraw after 12 hours, and for a limited 12 hour time frame once it is available. Scheduled withdrawals do not incur a % fee \(but gas fees are assessed for both transactions\). More details are available here
2. An **instant withdrawal** is processed immediately and you are assessed a small fee \(2%\) to withdraw.

![](../../.gitbook/assets/deets2.png)

## Liquidity Providers

{% hint style="warning" %}
LP incentive will be distributed every 5-9 days \(within this time frame at random intervals, for an average of every 7 days\) once the first distribution in launched. **We expect to launch the first distribution  in early September and will announce via** [**Twitter** ](https://twitter.com/xdaichain)**and** [**Telegram**](https://t.me/xdaistable) **when it is ready.**
{% endhint %}

If you are interested in supplying Liquidity in the form of STAKE / ETH and earning staking rewards as an LP,  you can add liquidity to the 🦄 Uniswap pool here: [https://uniswap.info/pair/0x3B3d4EeFDc603b232907a7f3d0Ed1Eea5C62b5f7](https://uniswap.info/pair/0x3B3d4EeFDc603b232907a7f3d0Ed1Eea5C62b5f7)

More details about liquidity provider rewards are available on the [EasyStaking page](./#liquidity-pool-lp-participants). 

STAKE/ETH pair contract on Etherscan: [https://etherscan.io/address/0x3b3d4eefdc603b232907a7f3d0ed1eea5c62b5f7](https://etherscan.io/address/0x3b3d4eefdc603b232907a7f3d0ed1eea5c62b5f7)

Distribution Contract: [https://etherscan.io/address/0x650c1c650773713e0884be96307fb0aa7f4ab070](https://etherscan.io/address/0x650c1c650773713e0884be96307fb0aa7f4ab070)

## Staking from a wallet without the UI

{% hint style="info" %}
We recommend users use the UI for EasyStaking - method below is available for contract interaction and other integrations.
{% endhint %}

You can transact with the EasyStaking proxy contract directly by sending STAKE to `0xecbCd6D7264e3c9eAc24C7130Ed3cd2B38F5A7AD`  . Once your transaction is approved, you can connect your wallet to the Easy Staking UI to view staking details.

_Note: Only send STAKE tokens to this address_

{% hint style="warning" %}
Instructions are in process for additional functionality such as using a Gnosis Multi-sig wallet. For more details about Easy Staking, please see the [EasyStaking page](./) and the [Parameters page](easy-staking-parameters.md).
{% endhint %}

