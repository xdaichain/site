# Creating your own Burner Wallet Token

Burner Wallet Factory provides the option to create a custom token for your wallet. This token can be "unbacked", which means it can be minted at any time in any amount, or "backed", which gives it value based on the backed collateral. By backing your coin with xDai, you know that each coin is also worth $1 USD.

Below, we will walk through the basic steps for creating a backed token on the xDai chain. For an excellent in-depth video on using BW Factory, see David Mihal, the creator of BW Factory, create and deploy a custom Spongebob token.

{% embed url="https://medium.com/@dmihal/token-factory-build-tokens-pop-up-economies-with-the-burner-factory-39ccea9f47ac" %}

For this tutorial, we will assume you have already created a wallet \(see [Creating a Quick Burner Wallet](creating-a-quick-burner-wallet.md)\). In this case, you will already be logged in to your account through Github.

1\) Go to **TOKENS** in the top menu and select **New Token**.

![](../../.gitbook/assets/token1.png)

![](../../.gitbook/assets/token2.png)

2\) Fill in the token details. 

* **Token Name**: Full name of your token
* **Token Symbol**: Unique Abbreviation, up to 5 characters
* **Maximum**: The maximum \(supply cap\) amount of tokens that can be created
* **Token Type**:  
  * **Backed**:  This means each token is backed by 1 xDai, making it worth 1 US Dollar
  * **Unbacked**: This is a token that is not backed by any currency, and can be minted in any amount up to the maximum. 
* **Network**: xDai.  For testing you can also deploy on Kovan or Gorli
* **Token Recovery Period**:  When creating an event token, you may want to create a recovery period where unused tokens can be swept back to the wallet. Options are Disabled, 1 Hour, 1 Day, 7 Days or 30 days
* **Icon**: Click to upload an image from your computer.

Click **Save and Publish.**

![](../../.gitbook/assets/token3.png)

3\) You will be forwarded to details about your newly created coin. Note that .01 xDai is added to any new token to pay for gas fees. In addition, the GSN \(Gas Station Network\) reload relay address is available for sending extra xDai if those funds run out.  \(.01 should be good for @ 500 transactions or so\).

![](../../.gitbook/assets/token4.png)

4\) Next, add your tokens to an existing wallet by selecting **Wallets** in the top navigation, going to the wallets screen, and **selecting your wallet**. Once you are in your wallet, Click on any asset. 

![](../../.gitbook/assets/token6.png)

5\)  In the popup select **ADD TOKEN**.

![](../../.gitbook/assets/token7.png)

6\) Choose a token from the list to add.

![](../../.gitbook/assets/token8.png)

7\) **Build and Deploy** your wallet again to add the new tokens.

![](../../.gitbook/assets/token9.png)

8\) You will now have tokens with a 0 balance. To populate, you can send some xDai to your wallet. Click on **Receive** at the bottom, then scan the QR \(or manually add\) to another wallet \(ie Metamask, AlphaWallet or similar\) that contains xDai, specifying the amount to send. 

9\) Once your wallet has some xDai, you can exchange it for other currencies. Click **Exchange** to start the process.

![](../../.gitbook/assets/token10.png)

10\) Select the xDai in the From: field, and one of your created tokens in the To field, and press **Exchange**.

![](../../.gitbook/assets/token11.png)

11\) Once a balance is shown, click the X to exit out of the Exchange window. Your new token balance will show!

![](../../.gitbook/assets/token12.png)

{% hint style="info" %}
We will add additional tutorials as items are added. Please check out [David Mihal on Medium ](https://medium.com/@dmihal)for more tutorials and information about the Burner Factory!
{% endhint %}

 



