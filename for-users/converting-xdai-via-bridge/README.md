---
description: Dai is converted to xDai through the TokenBridge
---

# Converting xDai via Bridge

## Bridge UI

{% hint style="success" %}
[https://dai-bridge.poa.network](https://dai-bridge.poa.network)
{% endhint %}

## What is the Bridge

The [TokenBridge](https://docs.tokenbridge.net/) is used to move and convert assets between chains.  With the xDai chain, the bridge converts Dai into xDai. Once converted, xDai is used as a native token \(for transactions as well as transaction fees\) on a chain where block times are fast and transactions are stable and extremely inexpensive. When a user is finished using xDai, they can convert it back to Dai using the same bridge.

The bridge uses smart contracts on both chains to process transfers, and a group of validators confirm bridge transactions. When a bridge transfer is initiated, the specified amount of Dai is locked in a smart contract on the Ethereum mainnet, and the same amount of xDai is minted on the xDai chain and sent to the user's wallet on the xDai chain.  When xDai is transferred back, xDai is burned, and the corresponding amount of Dai is unlocked in the contract and released to the user's wallet on the Ethereum mainnet.

The bridge mechanism ensures that the amount of xDai can never exceed the amount of Dai locked in the bridge contract.

## Dai/xDai Bridge Limits

| Type | Dai to xDai Bridge | xDai to Dai Bridge |
| :--- | :--- | :--- |
| Daily Transfer Limit | 10,000,000 Dai | 10,000,000 xDai |
| Max Single Deposit | 100,000 Dai | 100,000 xDai |
| Minimum Transfer | 0.005 Dai | 10 xDai |
| Transaction Fees | variable, paid in Eth | paid in xDai |
| Transfer Fees | 0%  | 0% |

## User Interface

A simple UI allows for seamless transfers between chains. Instructions for [moving Dai to xDai](moving-dai-to-xdai.md) and [moving xDai to Dai ](moving-xdai-to-dai.md)are available.  The bridge can also be used without a UI, [instructions are available here](https://docs.tokenbridge.net/xdai-bridge/how-to-use-xdai-bridge-without-ui).

![](../../.gitbook/assets/bridge.png)

