---
description: Set bridge to transfer funds to another address
---

# Alternate Receiver

The default bridge mode sends funds to the same address across chains. However, it is easy to specify another address to receive funds on the chain you are bridging to. This may be desirable when sending funds from a multi-sig wallet \([like Gnosis Safe](omnibridge-+-gnosis-safe-app.md)\), or as a transfer method to another address on a secondary chain.

## Set an Alternate Receiver:

1. Click on the Advanced link. A text field will appear. 
2. Paste in the 0x.... address you are transferring funds to on the receiving chain.
3. Proceed with the Request.

![](../../../.gitbook/assets/2021-05-06_12-22-37.gif)

{% hint style="info" %}
Claims on the receiving chain can be completed using any address with enough funds. Copy the tx hash from the first transaction \(it will be linked during tx processing or when complete in the history tab of the bridge. You can also find in your MetaMask wallet\) and paste into [https://alm-xdai.herokuapp.com/](https://alm-xdai.herokuapp.com/) to search and execute. 
{% endhint %}

![](../../../.gitbook/assets/hash-1.png)

{% hint style="info" %}
Another option is to connect to the bridge with the alternate receiver's address - the claim will be linked under History.
{% endhint %}

![](../../../.gitbook/assets/history1.png)

