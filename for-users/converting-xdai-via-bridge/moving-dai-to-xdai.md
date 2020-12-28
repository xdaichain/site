---
description: Transfer Dai to xDai through the simple UI
---

# Moving Dai to xDai

{% embed url="https://youtu.be/oKdh2cOOqUs" %}

{% hint style="info" %}
Notes: You will need some Dai to transfer \(minimum of 0.005 Dai\) AND some ETH for gas \(transaction fees\).

Bridge may take some time to update chain stats, try refreshing or waiting a minute if you receive any errors. You can also use a different RPC from the Settings dropdown.
{% endhint %}

1\) Go to [https://bridge.xdaichain.com/](https://bridge.xdaichain.com/). [Connect your web3 wallet](../wallets/metamask/metamask-setup.md) \(MetaMask, Nifty Wallet\) to the **Ethereum Mainnet**. Once connected, you will see your address populated in the header, and your DAI and xDai balance displayed on the page. 

_Note: If you change the dropdown on the page \(ETH Mainnet\) but not in MetaMask, the interface will shift but your wallet will not auto-connect to the chain. Switching chains in MM will automatically shift the interface._

2\) Enter the amount of Dai you would like to transfer to xDai, and click the **Transfer** button.

3\) The web3 wallet window will open with transaction details. Default gas price is fine, if you would like a faster transaction you can increase. Click **Submit or Confirm** \(depending on wallet\) to process the transaction.

![](../../.gitbook/assets/confirm.png)

4\) Wait for the transaction confirmation \(time depends on gas price and network throughput\). The transaction is considered finalized after 8 blocks. To check on a pending transaction, click on the tx in the UI.

![](../../.gitbook/assets/etherscan1.png)

![](../../.gitbook/assets/etherscan2.png)

{% hint style="info" %}
If TX is taking longer than 10 minutes \(usually due to rapid gas fluctuation on Ethereum\), you may want to try speeding it up. Press the **speed up button** in MetaMask and pay additional gas to help prioritize your tx for miners. This may result in a Dropped and Replaced status with a new tx hash. If you prefer to wait, the tx should resolve eventually, but in extreme cases can take up to 24 hours.
{% endhint %}

5\) Once the initial transaction is successful, you will see consecutive Transfer Pending notifications with:

1. 8 of 8 block confirmations.....
2. Countdown with continue until 1 block confirmation is left.
3. Waiting for execution on xDai Chain side.
4. Transfer Complete.

![](../../.gitbook/assets/tx-order.png)

6\) Click on View on BlockScout to see details about the transaction. If you scroll down you will see the address \(your address where the xdai was sent\), value \(amount sent in wei\), and transactionHash, which will match the hash from the initial transaction.

{% hint style="info" %}
If you are interested in converting Dai to xDai without the UI see [How to use xDai Bridge without UI](https://docs.tokenbridge.net/xdai-bridge/how-to-use-xdai-bridge-without-ui) 
{% endhint %}

