---
description: >-
  The perfect app for airdrops, populating burner wallets, or other occasions
  for sending xDai / ERC20 tokens to a group of addresses.
---

# Creating Airdrops with Token MultiSender

[Token MultiSender ](https://multisender.app/)is an efficient tool for sending airdrops to a large \(or small\) group of addresses. It bulk processes transfers into a small number of transactions, and distributes tokens for minimal fees.  Token MultiSender supports the xDai Chain as well as the Ethereum mainnet, testnets, [POA Network](https://poa.network) and others to send native or ERC20 tokens. 

In the following tutorial, we will airdrop xDai to a small number of addresses.

{% hint style="info" %}
When processing a large amount of addresses, transfers will be split into a small number of transactions \(up to 400+ per transaction\).   
  
For an example which sends ERC20 tokens to 1500 addresses and includes additional functionality, see the [MultiSender video tutorial](https://multisender.app/tutorial).
{% endhint %}

1\) Go to [https://multisender.app/](https://multisender.app/). You will be prompted to connect with your web3 enabled Ethereum wallet. Click **Connect**.

![](../../.gitbook/assets/connect1%20%281%29.png)

Connection options include include MetaMask, Portis or Squarelink. In this tutorial, we use [Nifty Wallet](../../for-users/wallets/nifty-wallet.md), which functions in a similar way to Metamask. Make sure your Nifty wallet is open and connected to the right account, then **select MetaMask** from the icons list.

{% hint style="warning" %}
If using MetaMask, you will need to [add xDai to the custom RPC list](../../for-users/wallets/metamask/metamask-setup.md). 
{% endhint %}

![Select your web3 wallet connection](../../.gitbook/assets/metamask1.png)

2\) **Select the token to airdrop**. You can choose to send any token you have in your wallet - the list of your tokens will appear in the dropdown.  We will choose to send **xDai - xDai Native Currency**.  Decimals will populate automatically \(18\) and Deflationary will be locked to no \(this is only used for specially designated tokens where a % of the supply is burned on every transaction\)

![Select a token to airdrop](../../.gitbook/assets/xdai1.png)

3\) **Enter in the list of Addresses and Amounts** amounts will be sent to - one `address,amount` per line. For example:

`0x7358ab3796a307fDe6961Ed10b92421c2F6dC871,0.01 0x8d61994A367df9FD41C0eBF93b62BD677fA5D60B,0.02`  
  
The list can be imported from a CSV file or entered manually. 

{% hint style="warning" %}
Note that amounts less than 1 unit must be start with a 0 \(for example .50 should be written as 0.50\). There should be no spaces between the address and amount, only comma separated.
{% endhint %}

![Token addresses and amounts to send](../../.gitbook/assets/token_list.png)

4\) Push Strategy will be auto-selected for sending xDai. Click the **Send** button to initiate the process.  

5\) You will be forwarded to a summary screen which displays information about the airdrop. Gwei will default to 2 Gwei, **change to 1** to save a small amount on transaction costs. Click **Proceed** to continue.

![Change to 1 Gwei for xDai transactions. Click Proceed to initiate the transaction.](../../.gitbook/assets/1gwei.png)

6\) Your web3 wallet will open to confirm the transaction. Click **Submit** to confirm.

![Click Submit to confirm the transaction in Nifty Wallet](../../.gitbook/assets/nifty_confirm.png)

7\) The transaction\(s\) will also be confirmed within seconds on the MultiSender page.

![Confirmation received in MultiSender](../../.gitbook/assets/trans_confirm.png)

8\) Check BlockScout for additional details about the transaction if desired.

![ Transaction details in BlockScout](../../.gitbook/assets/blcksct_confirmed.png)









