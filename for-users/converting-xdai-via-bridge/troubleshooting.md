# Troubleshooting and FAQs

Bridge transactions can take some time \(hours in extreme cases\) to complete depending on Ethereum mainnet congestion.  Try these actions first if your transaction has been **pending for 10 minutes or more** \(and you don't want to wait any more time\). Actions differ depending on if you are transferring from xDai to Dai or [Dai to xDai](troubleshooting.md#dai-to-xdai-transaction-is-taking-a-long-time).

## I transferred xDai to Dai but it's not working.

A new bridge decentralization feature means **withdrawals now require 2 steps**. You must initiate the bridge transaction on xDai, then claim your Dai on Ethereum. There are currently different bridging UIs, and depending on the UI you may need to take different steps to complete the process.

* \*\*\*\*[**xDai bridg**e](troubleshooting.md#i-used-the-xdai-bridge-ui) at [https://bridge.xdaichain.com/](https://bridge.xdaichain.com/) \(or [http://dai-bridge.poa.network/](http://dai-bridge.poa.network/) - this is another URL for the same app\)
* [**Burner Wallet**](troubleshooting.md#i-used-burner-wallet-at-xdai-io) at [xDai.io](https://xdai.io)
* \*\*\*\*[**xMoon exchange**](troubleshooting.md#i-used-xmoon-exchange) at [https://xmoon.exchange/](https://xmoon.exchange/)

## I Used the xDai Bridge UI

When using the xDai bridge, we recommend Chrome and MetaMask. It is also useful to disable ad blockers, as there are popups which guide you through the process.  [A successful transfer process is documented here](moving-xdai-to-dai.md).  

If you submitted a tx on xDai, but not complete the claim process, return to the Bridge Ui and connect your MetaMask \(MM\) wallet with the account you used previously. Click on **Haven't received your tokens**, switch MM to the ETH Mainnet, and paste in your transaction hash from the xDai transaction. [Need help finding your transaction hash?](find-a-transaction-hash.md) 

![](../../.gitbook/assets/claim1.jpg)

![](../../.gitbook/assets/claim2.jpg)

## I Used **Burner Wallet** at xDai.io

If you initiated a transfer from Burner Wallet, it likely is stuck on the Waiting for Bridge message.

![](../../.gitbook/assets/b1.jpg)

### I'm connected to the Burner Wallet with MetaMask

You can retrieve the pending transaction using the MetaMask interface. [Learn more here.](find-a-transaction-hash.md#find-transaction-hash-in-metamask)

1. Go to the Bridge UI at [https://bridge.xdaichain.com/](https://bridge.xdaichain.com/)
2. Click on **Haven't received your tokens** link under the ETH Mainnet side of the bridge.
3. Switch your MetaMask wallet to the ETH Mainnet
4. Paste in your transaction hash from the xDai transaction.
5. Press Claim.

### I'm using a standalone Burner Wallet

In this case, you'll want to export your private key into MetaMask to finish the conversion.

1\) Click the Advanced Button.

![](../../.gitbook/assets/a1.jpg)

2\)  Copy Private Key.

![](../../.gitbook/assets/a2.jpg)

3\) Open MetaMask and import the account.

![](../../.gitbook/assets/a3.jpg)

4\) Paste in the private key and click Import.

 

![](../../.gitbook/assets/a4.jpg)

5\)  Copy your wallet address.

![](../../.gitbook/assets/a5.jpg)

6\) Go to BlockScout at [https://blockscout.com/poa/xdai](https://blockscout.com/poa/xdai). Paste in your address to find the transaction, then copy the transaction hash.

![](../../.gitbook/assets/a6.jpg)

7\) Go to the Bridge UI at [https://bridge.xdaichain.com/](https://bridge.xdaichain.com/)

1. Click on **Haven't received your tokens** link under the ETH Mainnet side of the bridge.
2. Switch your MetaMask wallet to the ETH Mainnet
3. Paste in the transaction hash from the xDai transaction \(step 6\)
4. Press Claim.

{% hint style="info" %}
You will need some ETH in your wallet to pay gas fees and finalize the transaction. You can send from another account.
{% endhint %}

![](../../.gitbook/assets/a7.jpg)

8\) Confirm in MetaMask. 

![](../../.gitbook/assets/a8.jpg)

9. You will see a Success message when the transaction is complete.

![](../../.gitbook/assets/a9.jpg)

10. Add DAI as a custom token in MetaMask to view your DAI balance in the wallet.

![](../../.gitbook/assets/a10%20%281%29.jpg)

![](../../.gitbook/assets/a11%20%281%29.jpg)

![](../../.gitbook/assets/a12.jpg)

##  I Used **xmoon.exchange**

### I'm connected to the xmoon.exchange with MetaMask \(or another 3rd party wallet through wallet connect\)

You can retrieve the pending transaction using the MetaMask interface. [Learn more here.](find-a-transaction-hash.md#find-transaction-hash-in-metamask)

Once you have copied the transaction on xDai

1. Go to the Bridge UI at [https://bridge.xdaichain.com/](https://bridge.xdaichain.com/)
2. Click on **Haven't received your tokens** link under the ETH Mainnet side of the bridge.
3. Switch your MetaMask wallet to the ETH Mainnet
4. Paste in your transaction hash from the xDai transaction.
5. Press Claim.

The claim will process and you can view your Dai on Ethereum with the same wallet you used to initialize the transaction on xMoon.exchange.

### I'm using the burner wallet with xmoon.exchange \(not connected to any other wallet\)

_instructions in process - you will need to retrieve your private key to complete._

## Dai to xDai transaction is taking a long time

8 block confirmations are required to ensure a transaction is final and xDai can be minted to your account. If Ethereum is congested, it may take many more blocks for your transaction to be queued. If your transaction is stuck in pending for a long time, you can opt try to speed it up by selecting the pending transaction in MetaMask, clicking Speed Up, then paying the additional gas to try and get it through more quickly. Otherwise, it will likely be in a pending state until the congestion breaks up.

![](../../.gitbook/assets/speedup.jpg)









