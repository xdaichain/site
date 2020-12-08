# Move Stake



{% hint style="warning" %}
POSDAO Public Staking is not here yet \(anticipated Q4 2020\), but we are gathering documentation related to the xDai staking processes. All pages in this section are currently under construction. For staking available now, see [EasyStaking](../../easy-staking/)
{% endhint %}

To change which candidate you are staking on, or spread your stake to different pools, stake can be moved between pools. You must either retain the minimum amount of stake in the pool \(to remain in the pool\), or move the entire amount to exit the pool and shift your stake to a different pool. Stake moved to another pool must also total at least the minimum amount of stake. If you have already staked the minimum amount to a pool, you can move any additional amount to that pool.

### **Stake can be moved according to the following conditions:**

* Stake placed on an active candidate pool who is not a validator, or stake placed on an inactive candidate pool can be moved at any time\*
* Stake placed on an active validator pool can be moved **during the same staking epoch in which it was placed**.
* Stake cannot be moved or withdrawn from a banned pool until the ban is complete.

{% hint style="warning" %}
\*Note You cannot add, move or withdraw stake when the staking window is closed. This occurs at the very end of each staking epoch, where all staking actions are inactive.
{% endhint %}

## Move STAKE

1\) Locate the pool you would like to **move stake from**, and click the move stake icon. This icon will only appear if moving stake is a current option.

![](../../../.gitbook/assets/withdraw1%20%282%29.png)

2\)  Fill the following:

1. Amount to move:
   1.  You must keep the minimum amount in the current pool to remain a delegator, or remove the entire amount.
   2. You can move any amount to a target pool, but that pool must also have at least the minimum amount.
2. Choose a target pool from the dropdown list where you want to move the stake.
3. Click **Move Stake**.

![](../../../.gitbook/assets/withdraw2%20%281%29.png)

3\) When you select the target pool, the modal will change to display information about the **source pool** and the **target pool**.

4\) To proceed, click the **Move Stake** button. Confirm the transaction through the web3 wallet interface.

![](../../../.gitbook/assets/withdraw3.png)

5\) Once the transaction is complete, STAKE will be immediately removed from the current pool and placed in the selected pool.

6\) Moved stake is considered pending until the end of the current staking epoch. It can be moved an unlimited number of times until the staking window is close.

