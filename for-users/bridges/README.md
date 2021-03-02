---
description: xDai TokenBridges provide multi-chain compatibility and interoperability
---

# Bridges

* [xDai Bridge](converting-xdai-via-bridge/): Bridge from Ethereum to the xDai network designed for the xDai native token. Convert Dai to xDai and bridge xDai to Dai on Ethereum. 
* [Ethereum Omnibridge](omnibridge.md): Bridge ERC20 tokens between Ethereum and xDai. 
* [Binance Smart Chain OmniBridge](binance-smart-chain-omnibridge/): Bridge ERC20s between BSC and xDai. Provides beta access to inexpensive interoperability.

{% hint style="info" %}
For In-depth bridge specific documentation, please see the [TokenBridge Docs](https://docs.tokenbridge.net/).
{% endhint %}

With Multi-chain bridging, there is a possibility that multiple instances of the same underlying token can be created on a single chain. 

For example, USDT can be bridged to xDai from Ethereum and also bridged to xDai from BSC. This can result in 2 separate USDT token instances on xDai. These tokens cannot be merged into a single instance once they are minted. 

![Tether on xDai: 1 is bridged from ETH, the other from BSC](../../.gitbook/assets/tether-tether%20%281%29.png)

If you bridge and do not see the expected liquidity, for example in HoneySwap, know that there may be 2 instances of the same token on xDai. You will see a tag letting you know in an instance was bridged from Ethereum or BSC.

We are working on steps to address this issue in a decentralized manner without requiring prior approval to bridge. **Look for more details soon**.

