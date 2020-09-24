# Transfer Dai without the UI \(using MetaMask or an Ethereum Wallet\)

{% hint style="warning" %}
The bridge has been upgraded and Sai is no longer supported.
{% endhint %}

It is possible to move assets using a wallet rather than through the UI. This method is supported by all wallets that support ERC20 transfers \(e.g. [NiftyWallet ](https://chrome.google.com/webstore/detail/nifty-wallet/jbdaocneiiinmjbjlgalhcelgbejmnid?hl=en), [MyEtherWallet.com](http://myetherwallet.com/), [TrustWallet](https://trustwallet.com/), [MetaMask](https://metamask.io/)\). Here we use NiftyWallet.

Token address for reference:

* Dai: [0x6b175474e89094c44da98b954eedeac495271d0f](https://etherscan.io/token/0x6b175474e89094c44da98b954eedeac495271d0f)

TokenBridge addresses for reference \(where you send the asset to transfer\)

* Mainnet TokenBridge \(Dai -&gt; xDai\): `0x4aa42145Aa6Ebf72e164C9bBC74fbD3788045016`
* xDai TokenBridge \(xDai -&gt; Dai\): `0x7301CFA0e1756B71869E93d4e4Dca5c7d0eb0AA6`

## Transfer Dai from the Ethereum Mainnet to the xDai chain

1\) Connect to the Ethereum Mainnet and locate DAI in your webwallet. 

![](../../.gitbook/assets/sd1.png)

2\) Click Send

![](../../.gitbook/assets/sd2.png)

3\) Enter in the following:

1. TokenBridge Address as the recipient: `0x4aa42145Aa6Ebf72e164C9bBC74fbD3788045016`
2. Amount to Send
3. Press Next

![](../../.gitbook/assets/sd3.png)

4\) Submit the transaction

![](../../.gitbook/assets/sd4.png)

4\) Wait for the relay confirmation from the bridge validators. This may take several minutes.

5\) Set your wallet to the xDai chain and check your balance.

![](../../.gitbook/assets/sd5.png)

![](../../.gitbook/assets/sdbalance2.png)

### Transfer xDai to DAI from the xDai chain to the Ethereum Mainnet

{% hint style="success" %}
This process works the same way, start on the xDai chain and send the amount you would like to transfer to the xDai TokenBridge Address.
{% endhint %}

1\) Connect to the xDai chain. Send xDai to the TokenBridge address`0x7301CFA0e1756B71869E93d4e4Dca5c7d0eb0AA6`

2\) Wait for the transaction confirmation in the xDai chain \(5 seconds\).

3\) Wait for relay confirmation by the bridge validators \(depends on number of validators and the ETH Mainnet network throughput\)

4\) Switch to the mainnet and check your balance on the ETH Mainnet.





