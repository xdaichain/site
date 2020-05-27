---
description: For private round investors
---

# Claim STAKE: Private Investors

{% hint style="success" %}
STAKE token address on Ethereum [0x0Ae055097C6d159879521C384F1D2123D1f195e6](https://etherscan.io/token/0x0Ae055097C6d159879521C384F1D2123D1f195e6)

Private investor token contract  
[0x3cFE51b61E25750ab1426b0072e5D0cc5C30aAfA](https://etherscan.io/address/0x3cFE51b61E25750ab1426b0072e5D0cc5C30aAfA)
{% endhint %}

## Release Schedule

* Initial funds available 29.04.2020 for withdrawal \(25% released\)
* New funds available 27.05.2020 \(10%\) and each day following for the next 224 days. To transfer any available funds, you must follow the withdrawal process \(pull strategy\).

## MetaMask

{% hint style="warning" %}
If you have already setup MetaMask or other Web3Wallet with STAKE, skip to the [Token Withdrawal Section](claim-stake-pi.md#use-the-stake-token-withdrawal-dapp-to-transfer-stake-to-your-wallet)
{% endhint %}

{% hint style="info" %}
If using a hardware wallet to store your tokens \(Ledger, Trezor\) you can connect it to MetaMask rather than importing your account.  Connecting MetaMask instructions: [https://metamask.zendesk.com/hc/en-us/articles/360020394612-How-to-connect-a-Trezor-or-Ledger-Hardware-Wallet](https://metamask.zendesk.com/hc/en-us/articles/360020394612-How-to-connect-a-Trezor-or-Ledger-Hardware-Wallet)
{% endhint %}

1\) Import your account to MetaMask. This is the account you used to obtain STAKE as an Advisor or Private Investor. You can use the private key or JSON file to import \(or Connect Hardware Wallet\).

![](../../../.gitbook/assets/mm1.png)

2\) Add a small amount of ETH to your account to cover transactions \(.05 recommended\).

3\) Add the STAKE token to your wallet

a\) Click on the top left Menu 三  then press **Add token**

![](../../../.gitbook/assets/mm1%20%281%29.png)

b\)  Click the  **Custom Token** item and enter in the STAKE Token address. The remaining details will autopopulate. Click **Next**.  

* STAKE Token Address: [0x0Ae055097C6d159879521C384F1D2123D1f195e6](https://etherscan.io/token/0x0Ae055097C6d159879521C384F1D2123D1f195e6)

![](../../../.gitbook/assets/mm2.png)

c\) Click **Add Tokens** to add to your wallet view. You will have 0 STAKE tokens to start. In the next steps, you will add STAKE to your wallet.

![](../../../.gitbook/assets/mm3.png)

## Use the STAKE Token Withdrawal DApp to transfer STAKE to your wallet

4\) Go to [http://stake-token-withdrawal.xdaichain.com/](http://stake-token-withdrawal.xdaichain.com/)

5\) Connect MetaMask.

![](../../../.gitbook/assets/connect-1.png)

![](../../../.gitbook/assets/connect-2%20%281%29.png)

6\) Once connected you will see information related to your amount of STAKE. This includes:

* `Stake` Your total token amount.
* `Withdrawn` Amount of tokens you have already withdrawn.
* `Locked` Amount of tokens locked for future withdrawal.
* `Available` Amount of tokens available now. You will receive this amount when you process a withdrawal. 
* `Total number of installments`: Total installments \(224\).
* `Number of remaining installments`: How many daily installments are left.
* `Next installment`: Installments are released according to the following schedule:
  * 25% released at initialization
  * 10% released on Day 28
  * Daily installments for 224 days following day 28 

![](../../../.gitbook/assets/withdraw-stake.png)

7\) Press the **Withdraw\*** button to start the process. This will transfer the entire amount from **Available** to your **Wallet Address**. Confirm the transaction in the MetaMask popup.

{% hint style="warning" %}
\*Note - The **Withdraw** button is locked when **Available** is zero. If you see **Unlock funds** button under the **Withdraw**, click the Unlock Funds button to create a transaction to unlock the next installment. Confirming this transaction unlocks the installment for all addresses.
{% endhint %}

![MetaMask Confirmation](../../../.gitbook/assets/mm-confirm.png)

![\*Unlock funds button appears if no one has unlocked funds. Click to create an unlock transaction.](../../../.gitbook/assets/image%20%285%29.png)

{% hint style="success" %}
Once the withdrawal transaction is processed, you should see your STAKE token amount in MetaMask, and can transfer/send/exchange as you would any other ERC20 token.
{% endhint %}

## Optional Manual Instructions

If you have difficulty using the DApp or would prefer withdrawing manually, see the [Manual Instruction for Private Investors](manual-instruction-private-investors.md) which uses Etherscan to process the transfer.

