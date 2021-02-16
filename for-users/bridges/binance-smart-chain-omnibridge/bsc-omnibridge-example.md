---
description: Example transfer from xDai to BSC
---

# BSC OmniBridge Example

Here we show the bridging steps to transfer STAKE on xDai to STAKE on BSC. The chain names are appended, so the bridged token is called "STAKE on xDai on BSC".

## What you need:

* A [token on the xDai chain](https://blockscout.com/poa/xdai/bridged-tokens/eth) you want to swap.
* A small amount of xDai to complete the transfer. [Use the faucet if you just need some for transactions](https://blockscout.com/poa/xdai/faucet).
* BNB on the Binance Smart Chain. If you have BNB on BEP2 you will need to swap it to BSC. [Trust Wallet](https://trustwallet.com/) works well for this \(however Trust Wallet does not yet support xDai, so once you swap you'll need to send BNB from your Trust Wallet to your BSC address in MetaMask for this tutorial\).
* MetaMask custom RPCs [setup for xDai](../../wallets/metamask/metamask-setup.md) and for the Binance Smart Chain \( Network Name: BSC Mainnet New RPC URL: [https://bsc-dataseed.binance.org/](https://bsc-dataseed.binance.org/) ChainID: 56 Symbol: BNB Block Explorer URL: [https://bscscan.com/](https://bscscan.com/)\) or find [more detailed instructions here](https://docs.binance.org/smart-chain/wallet/metamask.html).

## Bridge STAKE from xDai to BSC

1\) Go to [https://bsc-to-xdai-omnibridge.web.app/](https://bsc-to-xdai-omnibridge.web.app/). 

1. Connect your web3 wallet to the xDai Network.
2. Select the token you want to bridge. 
3. Select the amount.
4. Click Unlock \(_note click Settings to enable infinite unlocks from this address rather that unlocking a specific amount to transfer_\).

![](../../../.gitbook/assets/omni1.png)

2\) Confirm the Unlock tx in MetaMask.

![](../../../.gitbook/assets/omni2.png)

3\) Once Unlock tx is complete, Request button will become active. Click Request and Confirm in MetaMask.

  


![](../../../.gitbook/assets/request.png)

![](../../../.gitbook/assets/omni3.png)

4\) Wait for **Block Confirmations** and **Signature Collections**. Once complete, you will see the message to switch the network to the Binance Smart Chain.

![](../../../.gitbook/assets/img4%20%282%29.png)

5\) Once you switch networks, you will see the claim button. 

1. Click to initiate claim the process. 
2. If the claim button does not work for some reason, you can click on the linked sending tx hash to process execute the transaction in the live monitor.

![](../../../.gitbook/assets/img5%20%281%29.png)

5a\) If using ALM, click on the Execute Button to finalize the claim.

![](../../../.gitbook/assets/alm1.png)

![](../../../.gitbook/assets/alm2.png)

6\) Once Claimed, you can click on the Receiving Tx to find your transaction on BscScan.

![](../../../.gitbook/assets/receiving.png)

{% embed url="https://bscscan.com/tx/0x9e7df2fae52bd7a36eb46a4ed7d6461a66f91128012e1e26ed780d28797caf55" %}

7\) To add STAKE to your BSC wallet, click on the Token Name, Copy the address, then go to custom token in MetaMask and add the address.

![Click on Token Name](../../../.gitbook/assets/tokenname.png)

![Copy Token Address](../../../.gitbook/assets/tokenaddress.png)

![Add as a Custom Token in MetaMask](../../../.gitbook/assets/tokentomm.png)



  
  
  


