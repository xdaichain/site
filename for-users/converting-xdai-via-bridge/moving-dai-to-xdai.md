---
description: Transfer Dai to xDai through the simple UI
---

# Moving Dai to xDai

1\) Go to [https://bridge.xdaichain.com/](https://bridge.xdaichain.com/). [Connect your web3 wallet](../wallets/metamask/metamask-setup.md) \(MetaMask, Nifty Wallet\) to the **Ethereum Mainnet**. Once connected, you will see your address populated in the header, and your DAI and xDai balance displayed on the page. 

{% hint style="success" %}
If you are experiencing issues or for personal preference, you can go to [https://xdai.io/](https://xdai.io/) and exchange using the burner application.
{% endhint %}

{% hint style="info" %}
You will need some Dai to transfer \(minimum of 0.005 Dai\) AND some ETH for gas \(transaction fees\).
{% endhint %}

![](../../.gitbook/assets/bridge1.jpg)

_Note: If you change the dropdown on the page \(ETH Mainnet\) but not in MetaMask, the interface will shift but your wallet will not auto-connect to the chain. Switching chains in MM will automatically shift the interface._

2\) Enter the amount of Dai you would like to transfer to xDai, and click the **Transfer** button.

3\) A confirmation window will appear. Click **Continue.**

![](../../.gitbook/assets/bridge2.jpeg)

4\) The web3 wallet window will open with transaction details. Default gas price is fine, if you would like a faster transaction you can increase. Click **Submit or Confirm** \(depending on wallet\) to process the transaction.

![](../../.gitbook/assets/bridge3.jpg)

5\) Wait for the transaction confirmation \(time depends on gas price and network throughput\). The transaction is considered finalized after 8 blocks. To check on a pending transaction, click on the tx in the Activity tab of MetaMask\(MM\).

![](../../.gitbook/assets/bridge4.jpg)

6\) Copy the tx hash.

![](../../.gitbook/assets/bridge5.jpg)

7\) Open Etherscan and paste the tx hash to view the current status.

![](../../.gitbook/assets/bridge6-etherscan.jpg)

{% hint style="info" %}
If TX is taking longer than 10 minutes \(usually due to rapid gas fluctuation on Ethereum\), you may want to try speeding it up. Press the **speed up button** in MetaMask \(see step 6\) and pay additional gas to help prioritize your tx for miners. If not, the tx should resolve eventually, but in extreme cases can take up to 24 hours.
{% endhint %}

8\) Confirmations are nearly complete. In a typical scenario, this process takes around 2 minutes.

![](../../.gitbook/assets/bridge7.jpg)

9\) Success! Dai has been bridged to xDai and available to use on the xDai chain. Switch your MetaMask wallet to xDai to see transfer. You can also click on the tx hash to view info about your transaction in BlockScout.

![](../../.gitbook/assets/bridge8.jpg)

![](../../.gitbook/assets/xdai22.jpg)

10\) Click on the tx hash to view details. If you scroll down you will see the address \(your address where the xdai was sent\), value \(amount sent in wei\), and transactionHash, which will match the hash from step 7 on the Ethereum Mainnet.

![](../../.gitbook/assets/bridge9.jpg)

{% hint style="info" %}
If you are interested in converting Dai to xDai without the UI see [How to use xDai Bridge without UI](https://docs.tokenbridge.net/xdai-bridge/how-to-use-xdai-bridge-without-ui) 
{% endhint %}

