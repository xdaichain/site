# Mint a Token \(unbacked\) on xDai in 5 minutes

🍬 In ****this tutorial we create and mint an unbacked token on the xDai chain. This type of token does not have any intrinsic value \(these tokens can be assigned value later however you choose to use them\). See our tutorial on [Creating your own backed token](creating-your-own-burner-wallet-token.md) if you want to create tokens from existing amounts of xDai.  

 We assume you have already created a wallet \(see [Creating a Quick Burner Wallet](creating-a-quick-burner-wallet.md)\) and are already logged into [Burner Factory ](www.burnerfactory.com)through Github. 

1\) Go to **TOKENS** in the top menu and select **New Token**.

![](../../.gitbook/assets/token1.png)

![](../../.gitbook/assets/bwnt1.png)

2\) Fill in the token details. 

* **Token Name**: Full name of your token
* **Token Symbol**: Unique Abbreviation, up to 5 characters
* **Maximum**: The maximum \(supply cap\) amount of tokens that can be created \(minted\)
* **Token Type**:  
  * **Backed**:  This means each token is backed by 1 xDai, making it worth 1 US Dollar
  * **Unbacked**: This is a token that is not backed by any currency, and can be minted in any amount up to the maximum. 
* **Network**: xDai.  For testing you can also deploy on Kovan or Görli.
* **Token Recovery Period**:  When creating an event token, you may want to create a recovery period where unused tokens can be swept back to the wallet. Options are Disabled, 1 Hour, 1 Day, 7 Days or 30 days
* **Icon**: Click to upload an image from your computer.

Click **Save and Publish.**

![](../../.gitbook/assets/bw-2.png)

3\) You will be forwarded to details about your newly created coin. It includes the token contract address, the vending machine address \(the contract with permission to mint and burn tokens\) and the Gas Station Network relay address you can send additional xDai to fund.

![](../../.gitbook/assets/bw-details.png)

{% hint style="info" %}
$.01 xDai is added to any new token to pay for gas fees. In addition, the GSN \(Gas Station Network\) reload relay address is available. You can send additional xDai here if the $.01 fund runs out.  \(.01 should be good for @ 500 transactions or so\).
{% endhint %}

4\) Mint some tokens to an address. 

1. Add the recipient's address.
2. Add the amount to mint \(up to the max amount\).
3. Click **Mint**.

![](../../.gitbook/assets/bw3.png)

5\) Check the transaction in BlockScout.

1. Address where the new tokens were minted. [0x27D6B8127e932eAbA1244bc3F3D87AEbE754abdf](https://blockscout.com/poa/xdai/address/0x27D6B8127e932eAbA1244bc3F3D87AEbE754abdf)
2. Transaction details \(token minting\). [0xb0acda6633abb1da8992c3c00f8545c459e37a7bb4de3fd59a394f3e4c52f56e](https://blockscout.com/poa/xdai/tx/0xb0acda6633abb1da8992c3c00f8545c459e37a7bb4de3fd59a394f3e4c52f56e)

![](../../.gitbook/assets/bw4.png)

![](../../.gitbook/assets/bw-bs1.png)

![](../../.gitbook/assets/bw-bs2.png)

{% hint style="success" %}
That's it. You can return to the token page to mint more tokens to different addresses as long as the total minting is =&lt; the total max amount of tokens. You can also send tokens to other addresses from within the Burner Wallet, or by adding the token contract to a web3 wallet connected to the xDai chain.
{% endhint %}

## Additional Resources

For an excellent in-depth video on using BW Factory, see David Mihal, the creator of BW Factory, create and deploy a custom Spongebob token.

{% embed url="https://medium.com/@dmihal/token-factory-build-tokens-pop-up-economies-with-the-burner-factory-39ccea9f47ac" %}

