---
description: Transfer Dai to xDai through the simple UI
---

# Moving Dai to xDai

1\) Go to [https://bridge.xdaichain.com/](https://bridge.xdaichain.com/). [Connect your web3 wallet](../wallets/metamask/metamask-setup.md) \(MetaMask, Nifty Wallet\) to the **Ethereum Mainnet**. Once connected, you will see your address populated in the header, and your DAI and xDai balance displayed on the page. 

{% hint style="success" %}
* If you are experiencing issues or for personal preference, you can go to [https://xdai.io/](https://xdai.io/) and exchange using the burner application.
{% endhint %}

{% hint style="info" %}
You will need some Dai to transfer \(minimum of 1 Dai\) as well as a small amount of ETH for transaction fees.
{% endhint %}

![Dai to xDai bridge interface](../../.gitbook/assets/screen-shot-2019-10-11-at-3.13.16-pm.png)

2\) Enter the amount of Dai you would like to transfer to xDai, and click the **Transfer** button.

3\) A confirmation window will appear. Click **Continue.**

![Confirmation window to confirm your transfer](../../.gitbook/assets/screen-shot-2019-10-11-at-3.13.23-pm.png)

4\) The web3 wallet window will open with transaction details. Default gas price is fine, if you would like a faster transaction you can increase. Click **Submit or Confirm** \(depending on wallet\) to process the transaction.

![Web3 Wallet \(Nifty Wallet\) confirmation. Default gas price is 1 Gwei.](../../.gitbook/assets/screen-shot-2019-10-11-at-3.13.33-pm.png)

5\) Wait for the transaction confirmation \(time depends on gas price and network throughput\). Typically, the transaction will be processed before the transaction relay is complete. We wait for 8 blocks before the transaction is considered finalized. 

![Transaction is processing](../../.gitbook/assets/screen-shot-2019-10-11-at-3.13.44-pm.png)

6\) Success! Dai has been transferred to xDai and is available for use on the xDai chain.

![Successful transfer from Dai to xDai](../../.gitbook/assets/screen-shot-2019-10-11-at-3.16.11-pm.png)

7\) Click on the transaction hex to view the transaction details in BlockScout. Here is our example transaction. [https://blockscout.com/poa/dai/tx/0x14faa1956887c70598292f3935a881993a02f39e98911af4f9f39426e4247c28](https://blockscout.com/poa/dai/tx/0x14faa1956887c70598292f3935a881993a02f39e98911af4f9f39426e4247c28)

{% hint style="info" %}
If you are interested in converting Dai to xDai without the UI see [How to use xDai Bridge without UI](https://docs.tokenbridge.net/xdai-bridge/how-to-use-xdai-bridge-without-ui) 
{% endhint %}

