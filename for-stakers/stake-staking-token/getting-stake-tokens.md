# Getting STAKE tokens

{% hint style="warning" %}
The following instructions are under construction and cover a test implementation on Kovan. Correct contract addresses will be added when the STAKE contract is live on the mainnet.
{% endhint %}

## Private Round Investors and Advisors 

Tokens will be available for withdrawal and use based on the distribution rules for your role. 

### Release Schedule

* **Private Investors**: 25% released at listing\*, 10% at day 28, remaining 65% distributed during the next 224 days.
* **Advisors**: 0% released at listing. Token release begins 84 days post listing and continues daily for 252 days.  _\* Available immediately using the_ [_withdrawal process_](getting-stake-tokens.md#withdrawal-to-your-wallet)\_\_

{% hint style="success" %}
**Requirements for this tutorial:** MetaMask, MyEtherWallet \(MEW\), Contract Addresses. You can use other methods \(such as Nifty Wallet\) to call contract functions if desired.
{% endhint %}

## Metamask / MEW

1\) Import your account to MetaMask. This is the account you used to obtain STAKE as an Advisor or Private Investor. You can use the private key or JSON file to import.

![](../../.gitbook/assets/mm1.png)

2\) Add a small amount of ETH to your account to cover transactions.

3\) Go to MyEtherWallet.com and login with MetaMask. 

1. Click **Access My Wallet**
2. Select MEW CX \(MetaMask\)

![Access my Wallet is on previous Screen. This is the Connection Screen \(2\)](../../.gitbook/assets/access-wallet.png)

4\) Go to Contract -&gt; Interact With Contract in the side menu.

![](../../.gitbook/assets/interact-w.png)

## **`makeInstallment` function**

5\) We will interact with the **Distribution Contract** to prepare an amount for withdrawal. The `makeInstallment` function is called to unlock amounts available for withdrawal. Amounts are available according to the release schedule. 

For example, 10% of a private investors amount will be available after day 28. This function is called after day 28 to prepare this amount for withdrawal. Each day following \(for the next 224 days\) a percentage of tokens is released, and each day this function may be called to prepare the corresponding amount for withdrawal.

If a day is skipped, that amount accrues. The total amount available is unlocked when the `makeInstallment` function is called.

{% hint style="info" %}
25% of Private Investor funds are available immediately once the STAKE token is listed. These can be accessed using the [withdrawal function](getting-stake-tokens.md#withdrawal-to-your-wallet) and does not need to be prepared. All other tokens releases must follow the prep process below.
{% endhint %}

5a\) Enter Contract Information:

* **Contract**: 0x99842cD4a57eD3a79ad8Cb9AE5747BEe1677Ab01
* **ABI**: [https://kovan.etherscan.io/address/0xC468a24d4E15c7A1e081394e24CE95E5D3b23554\#code](https://kovan.etherscan.io/address/0xC468a24d4E15c7A1e081394e24CE95E5D3b23554#code). Copy the ABI Code here and paste into the ABI/JSON Interface field. 
* Press **Continue**.

![Contract Address &amp; ABI](../../.gitbook/assets/continue-5.png)

![How to get the ABI code from Etherscan](../../.gitbook/assets/etherscan-abi.png)

5b\) Next screen:

1. Select the `makeInstallment` function from the dropdown menu. 
2. Enter a value in the \_pool\(unit8\) field. **This value depends on your role:**
   1. Private Investor: 3
   2. Advisor: 4
3. Click **Write**.

![](../../.gitbook/assets/makeinstallment.png)

5c\) Confirm the transaction in MetaMask.  


## **Withdrawal to your wallet**

6\)  Once the above transaction is complete \(or to withdraw initial private amount\), the installment amount is available to withdraw to your wallet.  Return to the **Interact with Contract** menu item and enter in the MultipleDistribution contract information. **Note the contracts are different for Private Investors and Advisors.** 

**Private Investor:**

* Contract: 0xC468a24d4E15c7A1e081394e24CE95E5D3b23554
* ABI: [https://kovan.etherscan.io/address/0xC468a24d4E15c7A1e081394e24CE95E5D3b23554\#code](https://kovan.etherscan.io/address/0xC468a24d4E15c7A1e081394e24CE95E5D3b23554#code)
* Click **Continue.**

**Advisor:**

* Contract: 0xD97921a3e85239A52A03C28bFFC2786A1372cf62
* ABI: [https://kovan.etherscan.io/address/0xd97921a3e85239a52a03c28bffc2786a1372cf62\#code](https://kovan.etherscan.io/address/0xd97921a3e85239a52a03c28bffc2786a1372cf62#code)
* Click **Continue.**

![Private Investor example](../../.gitbook/assets/contractw1.png)

6a\) Next Screen:

1. Select the **withdraw** function from the dropdown menu
2. Click **Write.**

![](../../.gitbook/assets/contract-withdraw.png)

6b\) Confirm the transaction in MetaMask ****then **Close** the Success Message.

![](../../.gitbook/assets/contract-w3.png)

7\) Checkout the transaction in EtherScan. The tx for this example withdrawal is:  [0x4036f11613402b964fa2602d6d849b2af00b52403c5ac625977c68d52374c2c5](https://kovan.etherscan.io/tx/0x4036f11613402b964fa2602d6d849b2af00b52403c5ac625977c68d52374c2c5)

![](../../.gitbook/assets/kovan-transaction-deets%20%281%29.png)

## Add STAKE token to MetaMask

8\) Tokens are now transferred to your wallet! To view, add the token to Metamask

8a\) Click on the Menu and select Add token

![](../../.gitbook/assets/mmk1.png)

8b\)  Click Custom Token and enter in the STAKE Token address. The remaining details will autopopulate. Click **Next**.  

* STAKE Token Address: [0xBB8685525257D89E8b104Ec4193565df67979023](https://kovan.etherscan.io/address/0xBB8685525257D89E8b104Ec4193565df67979023)

![](../../.gitbook/assets/mmk2.png)

8c\) Click **Add Tokens** to add to your wallet view.  You can now use or send STAKE as you would any other ERC20 token.

![](../../.gitbook/assets/mmk3.png)

  




\*\*\*\*





