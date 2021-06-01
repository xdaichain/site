# Hardware Wallets: Ledger & Trezor

Hardware wallets support includes Ledger & Trezor. The easiest way to use these wallets is to use MetaMask:

1\) Connect [MetaMask to the xDai Network](metamask/metamask-setup.md).  
2\) Select Connect Hardware Wallet from the MetaMask Dropdown.

![](../../.gitbook/assets/mm2%20%283%29.png)

3\) Connect your hardware wallet and select the hardware wallet account you want to interact with.

![](../../.gitbook/assets/mm-1%20%281%29.png)

4\) Once connected, your account will behave like any other MetaMask Account with the exception that you will sign and approve txs on your connected hardware device. As xDai is the native transactional token of the xDai chain, you may see xDai called ETH within the hardware wallet environment. 

{% hint style="info" %}
Additional instructions from the [MetaMask site here](https://metamask.zendesk.com/hc/en-us/articles/360020394612-How-to-connect-a-Trezor-or-Ledger-Hardware-Wallet) -&gt; note that there are some updates related to Chrome v91.
{% endhint %}

## Ledger

There is not an "xDai" dedicated application, you will use the [Ethereum application](https://support.ledger.com/hc/en-us/articles/115005200009-Set-up-and-use-MyEtherWallet) to interact with xDai through MetaMask.  Be sure your ledger firmware is updated and you have setup [Ledger Live](https://www.ledger.com/ledger-live/).

If interacting with a contract \(for example claiming tokens with a bridge transfer\), you will need to allow contract data.

1. Connect and unlock your Ledger device.
2. Open the **Ethereum** application.
3. Press the right button to navigate to **Settings**. Press both buttons to validate.
4. In the **Contract data** settings, press both buttons to allow contract data in transactions.  The device displays **Allowed**.
5. Retry your transaction.

For more help with Ledger, please see their [support docs](https://support.ledger.com/hc/en-us).

## Trezor

Once connected to the xDai network in MetaMask and your Trezor wallet, you will be forwarded to the [https://wallet.trezor.io](https://wallet.trezor.io/#/) interface to connect and complete transactions.



