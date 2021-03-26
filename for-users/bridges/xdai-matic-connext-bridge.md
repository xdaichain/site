---
description: Move xDai - Dai with the 3rd party Connext State Channels Bridge
---

# xDai &lt;-&gt; Polygon \(Matic\) State Channels Bridge Powered by Connext

{% hint style="info" %}
The xDai-Polygon \(Matic\) Bridge powered by [Connext](https://connext.network/) is developed by the [1Hive Collective](https://1hive.org/#/home), and not directly supported by the OmniBridge or xDai team. Use at your own risk. For questions or information, please see the [Connext Discord Channel](https://discord.gg/8YcWCfbp).
{% endhint %}

A new beta bridge lets users move xDai to Dai on Polygon \(Matic\), and Dai on Polygon \(Matic\) to xDai using state channels!  It's simple and inexpensive, and you can send any amount, large or small, between chains.

### Video

{% embed url="https://youtu.be/RlcyBtz3R2w" %}



## Text Explainer

### xDai to Polygon \(Matic\)

1\) Go to [https://xdai-matic-connext.vercel.app/](https://xdai-matic-connext.vercel.app/) and connect your web3Wallet. In this example we use MetaMask. If you need to add Matic or xDai, you can do so easily at [Chainlist.org](https://chainlist.org/). Also, if you are using Brave browser, disable shields.

![](../../.gitbook/assets/1connext.png)

2\) Connect to the chain you want to transfer from. 

1. Enter the Receiver's address \(it can be the same address on the other chain, or you can choose a different address.
2. Press Cross-Chain Transfer.

![](../../.gitbook/assets/2connext.png)

3\) Sign in your wallet to confirm channel setup.

![](../../.gitbook/assets/3connext.png)

4\) Enter the amount to transfer and press Swap.

![](../../.gitbook/assets/4connxt.png)

5\) Confirm the transaction in MetaMask. In this case the cross-bridge transfer cost $0.0004.

![](../../.gitbook/assets/connext5.png)

6\) Transaction should process in a few seconds and you will see success. You can click on the VIEW TX button to see the transaction in the Matic BlockScout Explorer.

![](../../.gitbook/assets/connext6.png)

![](../../.gitbook/assets/connext7.png)

7\) If bridging from xDai, and you have not added Dai to Matic previously, you may need to add to your wallet to view. Go to Assets -&gt; Add Token, enter the \(PoS\) Dai Stablecoin on Matic address: `0x8f3Cf7ad23Cd3CaDbD9735AFf958023239c6A063` and click Next to add to your wallet view.

![](../../.gitbook/assets/connextmm.png)

### Matic to xDai

To bridge in the other direction, simply change the chain in MetaMask, select the other direction, and proceed as above, this time moving Dai from Matic to xDai on the xDai chain.

{% hint style="info" %}
Note, you will need a very small amount of **Matic** to pay the transaction fees. Dai from Matic \([PoS Dai Stablecoin Dai](https://explorer-mainnet.maticvigil.com/tokens/0x8f3Cf7ad23Cd3CaDbD9735AFf958023239c6A063/token-transfers)\) will be converted to the xDai native token on the xDai chain.
{% endhint %}

![](../../.gitbook/assets/matic1.png)















