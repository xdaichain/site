---
description: >-
  Create ERC20 FAU tokens on xDai to test smart contracts and token transfer
  functionality
---

# ERC20 Test Token Faucet

The [ERC20 Token Faucet](https://erc20faucet.com/) by [peppersec](https://peppersec.com/) provides a sleek and easy interface for ERC20 test token creation. 

The faucet can quickly generate any number of FAU tokens directly from a web interface. These tokens are then available for developers to test smart contract applications and any other token transfer functionality.

### Prerequisites

* Network wallet address loaded with enough native currency \(xDai\) to cover the transaction.
* Web3 wallet interface such as [MetaMask](../../for-users/wallets/metamask/metamask-setup.md) or NiftyWallet. In this tutorial we use [NiftyWallet](https://forum.poa.network/t/nifty-wallet-is-back-on-the-chrome-store/2408).

{% hint style="info" %}
ERC20 Token Faucet can also be used with [Portis](https://www.portis.io/) or [Squarelink](https://squarelink.com/).
{% endhint %}

### Steps

1\) Go to [https://erc20faucet.com/](https://erc20faucet.com/).  Check that your web3 wallet \(ie NiftyWallet\) is connected to the xDai network. If you change this after step 3, you will need to reconnect.



![Connect to the xDai Chain](../../.gitbook/assets/xdai-connct.png)

2\) Click **Connect**.

![Click Connect to start the process](../../.gitbook/assets/connect_1.png)

3\) Select **Metamask**

![Connect with Metamask](../../.gitbook/assets/metamask_connect.png)

4\) Once selected, the web interface will populate with your Address, Network and Balance information.

* 1\) Select the **Amount of tokens** you would like to create.
* 2\) Click the **Mint Free Tokens** button.

![Enter Amount of tokens and click Mint Free Tokens to start the process](../../.gitbook/assets/token_2.png)

5\) Your web3 wallet interface should open. Check the transaction and click **Submit** to confirm. You will see a Success message if the transaction is successful.

![Click Submit to verify the transaction in Nifty Wallet](../../.gitbook/assets/nifty-2.png)

6\) The tokens have been minted on your address! To view them, you will need to add the Token Address to your wallet.

* A\) Copy the Token Address, open your NiftyWallet, and click Add Token in the Tokens tab.

![Add token to your wallet](../../.gitbook/assets/add-token.png)

* B\) Select the Custom tab, and paste in the Token Address from the website. The Token Symbol and Decimals should populate automatically. Click **Add**.

![Paste Token Address from erc20faucet into Nifty Token Address field](../../.gitbook/assets/click_add.png)

* C\) You should see your new FAU balance in the wallet.

![Fau Token is displayed in the Tokens area](../../.gitbook/assets/fau_end.png)

{% hint style="info" %}
To mint FAU tokens on another network, such as POA network, simply switch the network you are connected to in your web3 wallet, and follow the process above.
{% endhint %}

### Quick Video

This video shows the steps above using the POA network as a demo and a previous version of the ERC20 Token Faucet. Steps are identical, the only difference is the wallet must be connected to the **xDai Network**.

{% embed url="https://youtu.be/dngh8cVinZc" %}

{% hint style="success" %}
Instruction originally appeared on the POA forum [https://forum.poa.network/t/erc20-token-faucet-tutorial/2457](https://forum.poa.network/t/erc20-token-faucet-tutorial/2457)
{% endhint %}

