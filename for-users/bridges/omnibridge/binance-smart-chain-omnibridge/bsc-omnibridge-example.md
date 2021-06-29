---
description: Example transfer from xDai to BSC
---

# BSC OmniBridge Example

Here we show the bridging steps to transfer STAKE on xDai to STAKE on BSC. The chain names are appended, so the bridged token is called "STAKE on xDai on BSC".

## What you need:

* A [token on the xDai chain](https://blockscout.com/xdai/mainnet/bridged-tokens/eth) you want to swap.
* A small amount of xDai to complete the transfer. [Use the faucet if you just need some for transactions](https://blockscout.com/xdai/mainnet/faucet).
* BNB on the Binance Smart Chain. **You can now get BNB by transferring** [**wBNB from xDai**](wbnb-auto-conversion-to-bnb.md)**.** _If you have BNB on BEP2 you can also swap it to BSC._ [_Trust Wallet_](https://trustwallet.com/) _works well for this \(however Trust Wallet does not yet support xDai, so once you swap you'll need to send BNB from your Trust Wallet to your BSC address in MetaMask for this tutorial\)._
* MetaMask custom RPCs [setup for xDai](../../../wallets/metamask/metamask-setup.md) and for the Binance Smart Chain \( Network Name: BSC Mainnet New RPC URL: [https://bsc-dataseed.binance.org/](https://bsc-dataseed.binance.org/) ChainID: 56 Symbol: BNB Block Explorer URL: [https://bscscan.com/](https://bscscan.com/)\) or find [more detailed instructions here](https://docs.binance.org/smart-chain/wallet/metamask.html).

{% hint style="info" %}
If planning to bridge so you can trade an asset on BSC or xDai \(Honeyswap, BaoSwap etc\), **check liquidity for that asset on the chain where you want to trade prior to bridging**.   
  
In the example below we bridge STAKE on xDai to BSC, but there may not be enough liquidity for trading STAKE on BSC. In this case you can bridge it back to the originating chain \(or if its a supported stablecoin swap on [Component on xDai](https://xdai.component.finance/)\). 

Honeyswap liquidity pair resource: [https://www.liquidityfolio.com](https://www.liquidityfolio.com/#)
{% endhint %}

## Bridge STAKE from xDai to BSC

1\) Go to the OmniBridge at [https://omni.xdaichain.com/bridge](https://omni.xdaichain.com/bridge)

![](../../../../.gitbook/assets/bsc-1.png)

1. Connect your web3 wallet to the xDai Network. Select the **BSC &lt;-&gt; xDai** Bridge networks from the dropdown.
2. Select the token you want to bridge from your wallet on xDai to BSC.
3. Select the amount.
4. Click Unlock \(_note: you can also enable infinite unlocks. Click Settings to enable infinite unlocks from this address rather that unlocking a specific amount to transfer_\).

![](../../../../.gitbook/assets/bsc2.png)

2\) Confirm the Unlock tx in MetaMask.

![](../../../../.gitbook/assets/bsc-3.png)

3\) Once Unlock tx is complete, Request button will become active. Click Request and Confirm in MetaMask.

![](../../../../.gitbook/assets/request.png)

4\) Continue with the Transfer \(noting that there are 2 transactions to complete, one on xDai and a 2nd on the BSC chain\).

![](../../../../.gitbook/assets/bsc-confirm-1.png)

5\) Confirm in MetaMask. You can set GWEI to 1 to reduce costs.

![](../../../../.gitbook/assets/confirm-2%20%281%29.png)

6\) Wait for **Block Confirmations** and **Signature Collections**. Once complete, you will see the message to **switch the network to the Binance Smart Chain.**

![](../../../../.gitbook/assets/img4%20%282%29.png)

7\) Once you switch networks, you will see the claim button.

1. Click **Claim** to initiate claim the process. 
2. If the claim button does not work for some reason, you can click on the linked sending tx hash to process execute the transaction in the live monitor.

![](../../../../.gitbook/assets/img5%20%281%29.png)

7a\) If using ALM, click on the Execute Button to finalize the claim.

![](../../../../.gitbook/assets/alm1%20%281%29%20%281%29%20%281%29%20%282%29%20%282%29%20%282%29%20%282%29%20%282%29.png)

![](../../../../.gitbook/assets/alm2.png)

8\) Once Claimed, you can click on the Receiving Tx to find your transaction on BscScan.

![](../../../../.gitbook/assets/receiving.png)

{% embed url="https://bscscan.com/tx/0x9e7df2fae52bd7a36eb46a4ed7d6461a66f91128012e1e26ed780d28797caf55" caption="" %}

7\) To **add STAKE to your BSC wallet**, click on the Token Name, Copy the address, then go to custom token in MetaMask and add the address.

![Click on Token Name](../../../../.gitbook/assets/tokenname.png)

![Copy Token Address](../../../../.gitbook/assets/tokenaddress.png)

![Add as a Custom Token in MetaMask](../../../../.gitbook/assets/tokentomm.png)

