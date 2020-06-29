---
description: >-
  When distributing a group of wallets, you will likely want to supply them with
  xDai (for gas or event purchases) and event based tokens
---

# Airdrop tokens to an address set

1\) Go to the Distribution page and select the address set you created in the [Address Sets](./) instruction. Click on **ADD ASSET FOR AIR DROP** on the Account Set page. 

![](../../../../.gitbook/assets/airdrop1.png)

2\) A popup displays all current tokens, including any you have created. Select a token to add. If you are using the xDai network for your Burner wallet, add a little xDai so wallets can pay for transactions. \(If you are testing use Kovan or Gorli test eth\). Add token.

![](../../../../.gitbook/assets/airdrop2.png)

3\) Once added, you will see xDai: 0 balance for all accounts. Press **Distribute Funds**.

![](../../../../.gitbook/assets/distribute1.png)

4\) The Airdrop xDai popup will appear. You can send any amount to this contract address - the amount will be evenly distributed among all wallets in the set. For example, if you send 1 xDai and you have 100 wallets, each wallet will receive $.01 xDai. For a 1 day event, $.01 xDai is typically enough for each wallet, but you may want to add an extra cent or two depending on the number of participants. Each cent will cover ~500 transactions.

![](../../../../.gitbook/assets/distribute2.png)

{% hint style="info" %}
If you use Send with MetaMask, your MetaMask \(or Nifty Wallet\) account should be connected to the xDai chain, and the wallet should contain more than 1 xDai.  It will default to sending 1 xDai to distribute among all wallets.

Check the gas price when sending and adjust to 1-2 Gwei before submitting
{% endhint %}

5\) To add a second token, repeat steps 1-2,  selecting a second token. In this case we select the unbacked  "Spork" token. 

![](../../../../.gitbook/assets/spork.png)

6\) Press **Distribute Funds**.

![](../../../../.gitbook/assets/spork2.png)

7\) Enter the number of tokens to send to each address. Since SPORK is an unbacked token, any amount \(up to the maximum specified when creating a token\) can be minted and distributed. Click **MINT**.

![](../../../../.gitbook/assets/spork3.png)

8\) Each address will populate with the distributed tokens.

![](../../../../.gitbook/assets/populated%20%281%29.png)

{% hint style="info" %}
Wallets addresses are now supplied with initial token amounts. You can return to this page to add additional funds/tokens to wallet addresses at any time.  Next, you may want to [distribute paper wallets](distribute-paper-wallets.md).
{% endhint %}

## 

