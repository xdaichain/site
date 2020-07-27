# Manual Instructions - Advisors

{% hint style="success" %}
STAKE token address on Ethereum [0x0Ae055097C6d159879521C384F1D2123D1f195e6](https://etherscan.io/token/0x0Ae055097C6d159879521C384F1D2123D1f195e6)

Advisors token contract  
[0x0218B706898d234b85d2494DF21eB0677EaEa918](https://etherscan.io/address/0x0218B706898d234b85d2494DF21eB0677EaEa918)
{% endhint %}

## Release Schedule

* Initial funds available 22.07.2020 for withdrawal \(20% released\)
* New funds available each day following for the next 252 days. To transfer any available funds, you must follow the withdrawal process \(pull strategy\).

{% hint style="warning" %}
If you have already setup MetaMask, skip to the [Manual Instructions](https://www.xdaichain.com/for-stakers/stake-token/get-stake/manual-instructions-advisors#manual-instructions-use-etherscan-to-transfer-stake-to-your-wallet)
{% endhint %}

## MetaMask

{% hint style="info" %}
If using a hardware wallet to store your tokens \(Ledger, Trezor\) you can connect it to MetaMask rather than importing your account.  Connecting MetaMask instructions: [https://metamask.zendesk.com/hc/en-us/articles/360020394612-How-to-connect-a-Trezor-or-Ledger-Hardware-Wallet](https://metamask.zendesk.com/hc/en-us/articles/360020394612-How-to-connect-a-Trezor-or-Ledger-Hardware-Wallet)
{% endhint %}

1\) Import your account to MetaMask. **This is the account you used to obtain STAKE as an Advisor**. You can use the private key or JSON file to import \(or Connect Hardware Wallet\).

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

## Manual Instructions: Use Etherscan to transfer STAKE to your wallet

4\) Go to the following address on Etherscan.  
[https://etherscan.io/address/0x0218B706898d234b85d2494DF21eB0677EaEa918\#writeContract](https://etherscan.io/address/0x0218B706898d234b85d2494DF21eB0677EaEa918#writeContract)

5\) Connect MetaMask. Click on **Connect to Web3** and click **Connect**  on the MetaMask popup. 

![](../../../.gitbook/assets/advisor-1.png)

![](../../../.gitbook/assets/connect-2.png)

6\) In Etherscan, press the **Write** button next to the **withdraw** function.

![](../../../.gitbook/assets/advisor-2.png)

7\) Confirm the transaction details in MetaMask.

![](../../../.gitbook/assets/mm-confirm-advisor.png)

{% hint style="warning" %}
**Note**: If transaction fails, see the [unlock instructions]() below
{% endhint %}

8\) Click **View your transaction** to see transaction details

![](../../../.gitbook/assets/advisor-3.png)

{% hint style="success" %}
Once the transaction is processed, you should see your STAKE token amount in MetaMask, and can transfer/send as you would any other ERC20 token
{% endhint %}

**If MetaMask shows that your withdrawal transaction fails, try to unlock funds first:**

### **Unlock Instructions**

_Required if allotment has not yet been unlocked_

* Go to the following address on Etherscan: [https://etherscan.io/address/0x9BC4a93883C522D3C79c81c2999Aab52E2268d03\#writeContract](https://etherscan.io/address/0x9BC4a93883C522D3C79c81c2999Aab52E2268d03#writeContract)
* Connect MetaMask. Click on **Connect to Web3** and click **Connect** on the MetaMask popup.
* In Etherscan, find **makeInstallment** point, enter in **4** in **\_pool** text box, and then press the **Write** button:

![](../../../.gitbook/assets/advisor-install.png)

* After the **makeInstallment** transaction is processed \(confirm with MetaMask\), repeat the steps above \(starting from the step 4\) to call the **withdraw** function.



