# Troubleshooting

Bridge transactions can take some time \(hours in extreme cases\) to complete depending on Ethereum mainnet congestion.  Try these actions first if your transaction has been pending for 10 minutes or more \(and you don't want to wait any more time\). Actions differ depending on if you are transferring from Dai to xDai or xDai to Dai.

{% hint style="info" %}
More detailed instructions in process, basic actions below.
{% endhint %}

## Dai to xDai

8 block confirmations are required to ensure a transaction is final and xDai can be minted to your account. If Ethereum is congested, it may take many more blocks for your transaction to be queued. If your transaction is stuck in pending for a long time, you can opt try to speed it up by selecting the pending transaction in MetaMask, clicking Speed Up, then paying the additional gas to try and get it through more quickly. Otherwise, it will likely be in a pending state until the congestion breaks up.

![](../../.gitbook/assets/mm1.jpg)

## xDai to Dai

If your transfer is **processing for more than 10 minutes** and you have not received your Dai back, you can process it manually, bypassing some of the oracles components and submitting the signatures yourself. 

Copy the tx hash of the pending transaction on xDai. You can copy this from an xDai connected instance of MetaMask.

![Click on the pending transaction to get the tx hash](../../.gitbook/assets/mm2.jpg)

Go to [https://k1rill-fedoseev.github.io/manual-submit-signatures/](https://k1rill-fedoseev.github.io/manual-submit-signatures/)

1. Paste pending tx
2. Click Submit.
3. Check current gas prices to decide your limit. [https://ethgas.watch](https://ethgas.watch/) provides an aggregated price feed.
4. Click Confirm to process.

![](../../.gitbook/assets/mm3.jpg)





