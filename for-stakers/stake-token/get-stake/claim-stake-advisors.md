# Claim STAKE: Advisors

{% hint style="success" %}
STAKE token address on Ethereum [0x0Ae055097C6d159879521C384F1D2123D1f195e6](https://etherscan.io/token/0x0Ae055097C6d159879521C384F1D2123D1f195e6)
{% endhint %}

{% hint style="warning" %}
Tokens will not be available until 84 days post listing. Instructions will be updated prior to that time.
{% endhint %}

### Release Schedule

* **Advisors**: 0% released at listing. Token release begins 84 days post listing and continues daily for 252 days.

{% hint style="success" %}
**Requirements for this tutorial:** MetaMask, MyEtherWallet \(MEW\). You can use other methods \(such as Nifty Wallet\) to call contract functions if desired.
{% endhint %}

## Metamask / MEW

1\) Import your account to MetaMask. This is the account you used to obtain STAKE as an Advisor. You can use the private key or JSON file to import.

![](../../../.gitbook/assets/mm1.png)

2\) Add a small amount of ETH to your account to cover transactions.

3\) Go to MyEtherWallet.com and login with MetaMask. 

1. Click **Access My Wallet**
2. Select MEW CX \(MetaMask\)
3. Accept Terms and continue

![Access my Wallet is on previous Screen. This is the Connection Screen \(2\)](../../../.gitbook/assets/access-wallet.png)

4\) Go to Contract -&gt; Interact With Contract in the side menu.

![](../../../.gitbook/assets/interact-w.png)

## **`makeInstallment` function**

5\) We will interact with the **Distribution Contract** to prepare an amount for withdrawal. The `makeInstallment` function is called to unlock and transfer amounts available for withdrawal. Amounts are available to unlock according to the [release schedule](../stake-token-distribution/token-release-schedule.md). 

{% hint style="info" %}
Anyone can call `makeInstallment`. It unlocks the total amount of all funds \(Investors or Advisors\) within the schedule and transfers them to the appropriate contracts for [withdrawal](claim-stake-pi.md#withdrawal-to-your-wallet).
{% endhint %}

Each day following \(for the next 224 days\) a percentage of tokens is released, and each day this function may be called to prepare the corresponding amount for withdrawal.

If a day is skipped, that amount accrues. The total amount available for any role is unlocked within the schedule when the `makeInstallment` function is called.

5a\) Enter Contract Information:

* **Contract**: 0x9BC4a93883C522D3C79c81c2999Aab52E2268d03
* **ABI**: [https://etherscan.io/address/0x9BC4a93883C522D3C79c81c2999Aab52E2268d03\#code](https://etherscan.io/address/0x9BC4a93883C522D3C79c81c2999Aab52E2268d03#code)  Copy the ABI Code here and paste into the ABI/JSON Interface field. 
* Press **Continue**.

![Contract Address &amp; ABI](../../../.gitbook/assets/continue-5.png)

![How to get the ABI code from Etherscan](../../../.gitbook/assets/etherscan-abi.png)

5b\) Next screen:

1. Select the `makeInstallment` function from the dropdown menu. 
2. Enter a value in the \_pool\(unit8\) field. **This value depends on your role:**
   1. Private Investor: 3
   2. Advisor: 4 _Note: values can also release installments for the Ecosystem Fund: 1 or the Foundation Reward: 5_
3. Click **Write**.

![](../../../.gitbook/assets/makeinstallment.png)

5c\) Confirm the transaction in MetaMask. 

## **Withdrawal to your wallet**

6\)  Once `makeInstallment` has been called \(or to access initial private funds\), the withdraw function is used to move an available amount into your wallet. The withdraw function can be called any time after a single `makeInstallment` call or multiple `makeInstallment` calls. 

To start, return to the **Interact with Contract** menu item and enter in the MultipleDistribution contract information. 

**Advisor:**

* Contract: 0x0218B706898d234b85d2494DF21eB0677EaEa918
* ABI: [https://etherscan.io/address/0x0218B706898d234b85d2494DF21eB0677EaEa918\#code](https://etherscan.io/address/0x0218B706898d234b85d2494DF21eB0677EaEa918#code)
* Click **Continue.**

![Private Investor example](../../../.gitbook/assets/contractw1.png)

6a\) Next Screen:

1. Select the **withdraw** function from the dropdown menu
2. Click **Write.**

![](../../../.gitbook/assets/contract-withdraw.png)

6b\) Confirm the transaction in MetaMask ****then **Close** the Success Message.

![](../../../.gitbook/assets/contract-w3.png)

7\) Checkout the transaction in EtherScan. The tx for this example withdrawal is:  [0x4036f11613402b964fa2602d6d849b2af00b52403c5ac625977c68d52374c2c5](https://kovan.etherscan.io/tx/0x4036f11613402b964fa2602d6d849b2af00b52403c5ac625977c68d52374c2c5)

![](../../../.gitbook/assets/kovan-transaction-deets%20%281%29.png)

## Add STAKE token to MetaMask

8\) Tokens are now transferred to your wallet! To view, add the token to Metamask

8a\) Click on the Menu and select Add token

![](../../../.gitbook/assets/mmk1.png)

8b\)  Click Custom Token and enter in the STAKE Token address. The remaining details will autopopulate. Click **Next**.  

* STAKE Token Address: [0x0Ae055097C6d159879521C384F1D2123D1f195e6](https://etherscan.io/token/0x0Ae055097C6d159879521C384F1D2123D1f195e6)

![](../../../.gitbook/assets/mmk2.png)

8c\) Click **Add Tokens** to add to your wallet view.  You can now use or send STAKE as you would any other ERC20 token.

![](../../../.gitbook/assets/mmk3.png)

  




\*\*\*\*





