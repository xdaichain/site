# Become a Delegator

{% hint style="warning" %}
POSDAO Public Staking is not here yet but we are gathering documentation related to the xDai staking processes. All pages in this section are currently under construction. For staking available now, see [EasyStaking](../easy-staking/)
{% endhint %}

Delegators play an important role in securing the network. By placing stake on candidates, delegators provide additional funds which improve a candidate’s likelihood of becoming a validator. Stake can be thought of as a “vote” in the form of STAKE tokens for a candidate.

Delegators can place stake on multiple candidates, move stake between active candidates, and order stake withdrawals during a staking epoch. Block rewards for delegators are based on the percentage of stake they place in the pool. 

While each validator pool receives the same reward during a staking epoch, rewards within a pool are split between the validators and delegators. This split is based on how much stake a delegator has placed relative to the total pool stake \([delegators split up to 70% of the pool](../../about-xdai/faqs/)\). The reward percent is updated each staking epoch in the Delegators modal, which is accessed by clicking on the number of Delegators for any Pool.

{% embed url="https://youtu.be/DVSqVaut\_Vc" caption="How to Delegate STAKE using BlockScout" %}

## **Delegating STAKE**

1\) You will need the minimum delegator stake amount of STAKE \(currently 1000 STAKE\) and a small amount of xDAI \(.1 is plenty\) deposited to your address on the xDai chain.

* [Move DAI to xDai](../../for-users/converting-xdai-via-bridge/)
* Video: [Move Stake from Ethereum to xDai with the OmniBridge](https://youtu.be/qbuBqur9lcE).

2\) Go to [blockscout.com](http://blockscout.com/) and change the network to the xDai network.

3\) After you have switched to xDai, select an item from the Stakes dropdown.

4\) Set your web3wallet  ccount to the address which contains xDai and STAKE, and set the RPC network in the wallet to xDai. Once connected, you should see your address and STAKE balance in the site banner.

![](../../.gitbook/assets/header1.png)

5\) Find a candidate pool you would like to place stake on. You can view **current validator pools** on the **Validators Tab**, and **all active pools** in the **Active Tab** \(_this includes validators as well as pools which are not currently validating but are eligible to become validators_\). 

Click on the pool address to see current pool statistics to help guide your decision. Staking into a candidate with a smaller pool size will result in higher reward percentages, however, candidates with smaller pools have a lower likelihood of selection to the validator set \(assuming 20+ active pools\). Stake on the candidate\(s\) you believe will provide the most benefits for the network; this will benefit you as well. You can also learn more about validators at [https://dai-netstat.poa.network/](https://dai-netstat.poa.network/)

6\) Once decided, click the stake icon next to the pool you would like to stake on.

![](../../.gitbook/assets/stake-header-2.png)

7\) Enter the STAKE amount to stake. The minimum initial stake is 1000. Click the **Place Stake** button to submit your transaction.

8\) You should see the transaction pop-up for your web3 wallet. Transaction fees do not need to change. Click **submit** to process.

9\) Wait a moment for successful processing. Once confirmed, you will see the Success modal. Click OK.

10\) Your stake will be added to the pool. **It will not be activated until the next staking epoch**. This means you can move or withdraw your stake freely until the staking window closes, which occurs at the end of the current staking epoch.

11\) To view your stake amount and reward percentage, click on the number of delegators. Your address will be marked with **ME**.

![](../../.gitbook/assets/header3.png)

12\) If the pool you delegate to is selected as a validator for the next validator set, your STAKE will accrue rewards. Rewards are accrued to contract's balance and can be claimed with **Claim Reward** feature.

13\) While your delegator stake is active \(in use by a current validator pool\), it cannot be withdrawn immediately. However, you can:

1. **Add additional stake**: Any additional stake added during an epoch will not accrue rewards for the current epoch, but will be added to the pool size which will influence selection in the next epoch. If the pool is chosen as a validator again, this added stake will be included in the next epoch’s rewards calculations.  


   \*\*\*\*💎 **Instruction** To add additional stake on a candidate or validator, click the stake icon and enter the additional amount. You can add in any increment, as long as the total stake is more than a minimal required amount. Follow the web3 wallet prompts to complete the transaction. [More Info](staking-operations/add-stake.md)  

2. **Order stake for withdrawal**. You may order a withdrawal of your stake, which will be available after the current epoch ends. Ordering a withdrawal will also influence total pool size for the next epoch’s selection process.To order a withdrawal, click the withdrawal icon and enter the amount to order. You must either keep the minimum delegation stake amount OR order the entire amount for withdrawal. You cannot have an amount below the minimum, but you may withdraw your total amount.  


   \*\*\*\*💎 **Instruction** Enter the amount and click Order Withdrawal. You can enter the whole amount to remove yourself as a delegator, or you can remove a portion as long as you maintain a minimum of 1000 STAKE.The transaction should process through the web3 wallet interface. Once the staking epoch is complete, the amount will be available to claim. Click on the claim icon and follow the instructions. [More Info](staking-operations/withdraw-stake.md#ordered-withdrawal)

