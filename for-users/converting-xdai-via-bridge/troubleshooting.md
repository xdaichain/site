---
description: Resolving bridge issues
---

# Troubleshoot Bridge Txs, UI, xDai.io, xmoon.exchange, MetaMask

Bridge transactions can take some time \(hours in extreme cases\) to complete depending on Ethereum mainnet congestion.  Try these actions first if your transaction has been **pending for 10 minutes or more** \(and you don't want to wait any more time\). Actions differ depending on if you are transferring from xDai to Dai or [Dai to xDai](troubleshooting.md#dai-to-xdai-transaction-is-taking-a-long-time).

If you are using OmniBridge for other ERC20 tokens \(not xDai &lt;-&gt; Dai\) please see the [OmniBridge page](../omnibridge.md). **This guide only addresses issues with xDai to Dai transfers.**

## Bridge UI is Offline or in Maintenance Mode

We are doing some periodic maintenance and optimization on the Bridge and are now putting the UI into maintenance mode during these times to avoid additional confusion and/or delayed transactions for users. If you started a transaction but it did not complete because of maintenance mode, be assured that funds are safe and will be available once maintenance is complete. If you have questions or concerns during maintenance, please contact us in [Discord channel ](https://discord.gg/mPJ9zkq)for up-to-date information.

## I Only See Bridging in 1 Direction

The bridge is dynamic and supports bi-directional bridging. It will shift automatically when you update your web3wallet \(MetaMask\) to the correct chain. When you are on Ethereum Mainnet, you will see the Eth-Mainnet to xDai chain side, and when you are on xDai, you will see the xDai to Eth Mainnet side. You can adjust which side through the Bridge toggle in menu, however to initiate a transfer you will need your wallet set to the correct chain.

![Toggle to switch bridge side in UI - You will also need to adjust MetaMask.](../../.gitbook/assets/toggle1.png)



## I Transferred xDai to Dai but it's Not Working

A new bridge decentralization feature means **withdrawals now require 2 steps**. You must 

1. initiate the bridge transaction on xDai
2. Claim your Dai on Ethereum. 

There are currently different bridging UIs, and depending on the UI you may need to take different steps to complete the process.

* \*\*\*\*[**xDai bridg**e](troubleshooting.md#i-used-the-xdai-bridge-ui) at [https://bridge.xdaichain.com/](https://bridge.xdaichain.com/) \(or [http://dai-bridge.poa.network/](http://dai-bridge.poa.network/) - this is another URL for the same app\)
* [**Burner Wallet**](troubleshooting.md#i-used-burner-wallet-at-xdai-io) at [xDai.io](https://xdai.io)
* \*\*\*\*[**xMoon exchange**](troubleshooting.md#i-used-xmoon-exchange) at [https://xmoon.exchange/](https://xmoon.exchange/)

## I Used the xDai Bridge UI

When using the xDai bridge, we recommend Chrome and MetaMask. It is also useful to disable ad blockers, as there are popups which guide you through the process.  [A successful transfer process is documented here](moving-xdai-to-dai.md).  

If you submitted a tx on xDai, but not complete the claim process, return to the Bridge Ui and connect your MetaMask \(MM\) wallet with the account you used previously. 

1. Switch MM to the ETH Mainnet.
2. Click on **Haven't received your tokens**

![](../../.gitbook/assets/eth1.jpg)

A modal will appear with 2 possible states. You will either see:

1. A list of transactions you have not claimed
2. A message that says "You don't have tokens to claim. If you have any questions please contact us on social networks."

{% hint style="info" %}
If your initial transaction from xDai to the bridge was processed recently, wait a few minutes. Typically a transaction will take 6 minutes to display. 
{% endhint %}

### List of transactions to claim

Click the Claim link to begin the process. MetaMask will ask you to confirm the transaction and pay the gas fees to complete the process.

![](../../.gitbook/assets/claim11%20%281%29.jpg)

### You don't have tokens to claim

This can occur for several reasons. The claim may not yet be processed, or you are claiming with a different address \(for example the initial tx was completed by a contract or another address\). In this case, once the first tx to the bridge is complete, click **Enter transaction hash manually**.

![](../../.gitbook/assets/claim12.jpg)

Enter in the transaction hash from the xDai bridge and press Claim to start the process. More on [finding the transaction hash here.](find-a-transaction-hash.md)

![](../../.gitbook/assets/claim13.jpg)

If for some reason the process continues to present issues, contact the team in [Discord](https://discord.gg/mPJ9zkq).

## I Used **Burner Wallet** at xDai.io

If you initiated a transfer from Burner Wallet, it likely is stuck on the Waiting for Bridge message.

![](../../.gitbook/assets/b1.jpg)

### I'm connected to the Burner Wallet with MetaMask

You can retrieve the pending transaction using the MetaMask interface. [Learn more here.](find-a-transaction-hash.md#find-transaction-hash-in-metamask)

1. Go to the Bridge UI at [https://bridge.xdaichain.com/](https://bridge.xdaichain.com/)
2. Switch your MetaMask wallet to the ETH Mainnet
3. Click on **Haven't received your tokens** link under the ETH Mainnet side of the bridge.
4. If you see a transaction to claim, press the **Claim** link**.** _\(will not appear until 6+ minutes after the transaction\)_
5. If not, click on **Enter Transaction Hash Manually** and paste in your transaction hash from the xDai transaction.
   1. Press Claim.
6. **Confirm** transaction in MetaMask and wait for tx validation.

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

5\) Go to the Bridge UI at [https://bridge.xdaichain.com/](https://bridge.xdaichain.com/)

1. Switch your MetaMask wallet to the ETH Mainnet
2. Click on **Haven't received your tokens** link under the ETH Mainnet side of the bridge.
3. If you see a transaction to claim, press the **Claim** link _\(will not appear until 6+ minutes after the transaction\)._
4. If not, click on **Enter Transaction Hash Manually** and paste in your transaction hash from the xDai transaction. [If you need the transaction hash, you can copy your wallet address and find it in Blockscout.](find-a-transaction-hash.md)
5. Press Claim.
6. **Confirm** transaction in MetaMask and wait for tx validation.

{% hint style="info" %}
You will need some ETH in your wallet to pay gas fees and finalize the transaction. You can send from another account.
{% endhint %}

 

6\)  You will see a Success message when the transaction is complete.

![](../../.gitbook/assets/a9.jpg)

7\) Add DAI as a custom token in MetaMask to view your DAI balance in the wallet.

![](../../.gitbook/assets/a10%20%281%29.jpg)

![](../../.gitbook/assets/a11%20%281%29.jpg)

![](../../.gitbook/assets/a12.jpg)

##  I Used **xmoon.exchange**

### I'm connected to the xmoon.exchange with MetaMask \(or another 3rd party wallet through wallet connect\)

You can retrieve the pending transaction using the MetaMask interface. [Learn more here.](find-a-transaction-hash.md#find-transaction-hash-in-metamask)

Once you have copied the transaction on xDai

1.  Go to the Bridge UI at [https://bridge.xdaichain.com/](https://bridge.xdaichain.com/)
   1. Switch your MetaMask wallet to the ETH Mainnet
   2. Click on **Haven't received your tokens** link under the ETH Mainnet side of the bridge.
   3. If you see a transaction to claim, press the **Claim** link _\(will not appear until 6+ minutes after the transaction\)._
   4. If not, click on **Enter Transaction Hash Manually** and paste in your transaction hash from the xDai transaction. [If you need the transaction hash, you can copy your wallet address and find it in Blockscout.](find-a-transaction-hash.md)
   5. Press Claim.
   6. **Confirm** transaction in MetaMask and wait for tx validation.

The claim will process and you can view your Dai on Ethereum with the same wallet you used to initialize the transaction on xMoon.exchange.

### I'm using the burner wallet with xmoon.exchange \(not connected to any other wallet\)

_instructions in process - you will need to retrieve your private key to complete._

## Dai to xDai Transaction is Taking a Long Time

8 block confirmations are required to ensure a transaction is final and xDai can be minted to your account. If Ethereum is congested, it may take many more blocks for your transaction to be queued. If your transaction is stuck in pending for a long time, you can opt try to speed it up by selecting the pending transaction in MetaMask, clicking Speed Up, then paying the additional gas to try and get it through more quickly. Otherwise, it will likely be in a pending state until the congestion breaks up.

If it remains in a pending state on MetaMask for a long time, see [Resetting MetaMask ](troubleshooting.md#transaction-not-showing-on-blockscout-or-etherscan-resetting-metamask)below.

![](../../.gitbook/assets/speedup.jpg)

## Transaction Not Showing on BlockScout or Etherscan - Resetting MetaMask.

If you initiated a transaction but don't see a pending transaction the Block Explorer \(in either direction, if originating from xDai check [BlockScout](https://blockscout.com/poa/xdai), if Ethereum check [Etherscan](https://etherscan.io/)\) try resetting your MetaMask account to clear your transaction history.

This can be useful to clear up:

* A pending transaction which refuses to clear.
* A transaction fails to show up on Etherscan but is still pending.

{% hint style="warning" %}
Imported accounts will not repopulate win your wallet with this method, so be sure you have access to a private key or seed phrase to restore these in a reset account.
{% endhint %}

{% embed url="https://metamask.zendesk.com/hc/en-us/articles/360015488891-Resetting-an-Account" %}

## I'm using a Ledger to Claim tokens on an xDai to Dai Bridge Transfer

To use a Ledger you need to allow contract data in order to interact with smart contracts. We assume that you have installed the [Ethereum app](https://support.ledger.com/hc/en-us/articles/115005200009-Set-up-and-use-MyEtherWallet).

1.  [Update the firmware](https://support.ledgerwallet.com/hc/en-us/articles/360002731113) to the latest version.
2. Connect and unlock your Ledger device.
3. Open the **Ethereum** application.
4. Press the right button to navigate to **Settings**. Press both buttons to validate.
5. In the **Contract data** settings, press both buttons to allow contract data in transactions.  The device displays **Allowed**.
6. Retry your transaction.

For more help with Ledger, please see their [support docs](https://support.ledger.com/hc/en-us).







