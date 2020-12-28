---
description: Convert xDai back to Dai in the UI
---

# Moving xDai to Dai

{% embed url="https://youtu.be/oKdh2cOOqUs?t=105" caption="xDai - Dai transfers begin at 1:45" %}



{% hint style="info" %}
We recommend using Chrome + Metamask + No Ad Blockers to complete the process.  
  
You will need a **small additional amount of xDai** to process the first transaction, and an **additional amount of Eth** to process the claim transaction on Ethereum.
{% endhint %}

{% hint style="warning" %}
**Important Update**: The xDai bridge has been updated to decentralize withdrawals and give users more control when transferring xDai to Dai on Ethereum. [More information is here](https://forum.poa.network/t/important-changes-in-a-user-interaction-with-the-xdai-bridge/3906).   
  
If you did not use the Bridge UI to process your original bridge request - for example you used xDai.io, a contract call or another platform, you may need to [**find the first transaction hash**](find-a-transaction-hash.md) ****and use the ****[**claim function on the bridge**](find-a-transaction-hash.md#claim-your-tokens) \(click on **Haven't received your tokens**\) to complete your transfer.

If you experience issues, see the [Troubleshooting page](troubleshooting.md).
{% endhint %}

1\) Go to [https://bridge.xdaichain.com/](https://bridge.xdaichain.com/). [Connect your web3 wallet](../wallets/metamask/metamask-setup.md) \(MetaMask, Nifty Wallet\) to the **xDai Chain**. Once connected, you will see your address populated in the header, and your xDai and Dai balance displayed on the page.  

_Note: If you change the dropdown on the page \(xDai Chain\) but not in MetaMask, the interface will shift but your wallet will not auto-connect to the chain. Switching chains in MM will automatically shift the interface._

![](../../.gitbook/assets/xdai-to-mainnet.png)

2\) Enter the amount of xDai you would like to transfer to Dai, and click the **Transfer** button. Note the **minimum amount is 10 xDai.**

3\) A confirmation modal will appear. Click **Continue.**

{% hint style="info" %}
New screenshots coming soon to reflect the updated Bridge UI
{% endhint %}

![](../../.gitbook/assets/1new.jpg)

4\) The web3 wallet window will open with transaction details. Click **Submit or Confirm** \(depending on wallet\) to process the transaction.

![](../../.gitbook/assets/2new.jpg)

5\) Wait for the transaction on xDai to process. 

![](../../.gitbook/assets/3new.jpg)

6\) You will see a modal to switch networks in your MetaMask \(or other web3\) to the Ethereum Network.

![](../../.gitbook/assets/4new.jpg)

7\) Press the **Claim** button.

![](../../.gitbook/assets/5n32.jpg)

8\) **Confirm** the transaction in MetaMask. You will need some ETH to confirm and complete the transaction.

![](../../.gitbook/assets/6new.jpg)

9\) Wait for confirmations from validators on Mainnet. Once this is complete, you should see the Success message.  xDai has been transferred to Dai and is available for use on the Ethereum mainnet.

![](../../.gitbook/assets/7new.jpg)

9\) Click the transaction hex to view your transaction in Etherscan.

![](../../.gitbook/assets/8new.jpg)

{% hint style="info" %}
If you are interested in converting Dai to xDai without the UI see [how to use xDai Bridge without UI](https://docs.tokenbridge.net/xdai-bridge/how-to-use-xdai-bridge-without-ui) 
{% endhint %}

