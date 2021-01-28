---
description: Using STAKE in a Multisig Gnosis Safe for voting on snapshot
---

# Delegate STAKE voting weight with Gnosis Safe

STAKE held in an EOA \(externally owned address\) on Ethereum and [staked on EasyStaking](https://easy-staking.xdaichain.com/deposits) can be used for [stake weighted voting with snapshot](https://snapshot.page/#/xdaistake.eth). STAKE held in a Gnosis Safe multisig account cannot be directly used from that account for voting purposes. However, it can be delegated to an EOA and then used for stake weighted voting. The delegated amount is added to any additional STAKE held in a wallet or in EasyStaking, providing a total signaling weight for voting purposes. 

1\) Go to Snapshot [https://snapshot.page/\#/xdaistake.eth](https://snapshot.page/#/xdaistake.eth) and Connect wallet with Wallet Connect.

![](../../../.gitbook/assets/gnosis-safe1.png)

2\) Copy QR Code.

![](../../../.gitbook/assets/gnosis-qr.png)

3\) Login to your Gnosis Safe and Go to Apps, Wallet Connect.

![](../../../.gitbook/assets/gnosis-apps-wallet-connect.png)

4\) Paste in the copied code.

![](../../../.gitbook/assets/gnosis-pasted-code.png)

![](../../../.gitbook/assets/connected.png)

5\) Return to Snapshot and go to the delegate page at [https://snapshot.page/\#/delegate](https://snapshot.page/#/delegate). Enter in the address you would like to delegate to and click confirm. 

![](../../../.gitbook/assets/delegate-on-snap.png)

6\) With the related multi-sig threshold, safe users will then need to **submit the transaction and pay gas fees through the Gnosis Safe**. 

![](../../../.gitbook/assets/submit-in-safe.png)

7\) Once confirmed you will see the address you have delegated to. If tx is successful and has been submitted for some time but you do not see the address, refresh the page.

![](../../../.gitbook/assets/confirmed.png)

8\) **Logout from your Safe address** in snapshot and click Connect to **login with the address you have delegated to**. 

![Logout the safe address](../../../.gitbook/assets/logout.png)

![login with delegation address](../../../.gitbook/assets/login.png)

9\) Go to the proposal and vote. Stake weight should be reflected from the Gnosis safe, as well as other sources \(like existing STAKE in your wallet or stake in EasyStaking\). [More on general voting process here.](./)

![](../../../.gitbook/assets/voting-power-1.png)

![](../../../.gitbook/assets/votingpower2.png)

{% hint style="info" %}
More info in Gnosis Governance Tutorial: [https://blog.gnosis.pm/gnosisdao-governance-tutorial-8257f5a1adb4\#7c45](https://blog.gnosis.pm/gnosisdao-governance-tutorial-8257f5a1adb4#7c45)

**Important**: For a delegated address to be effective when signaling on a Snapshot poll, the address has to have been delegated to by the block number set on the Snapshot poll.

**Related**: It is possible to change the delegation address. However, if the original delegated address has already voted on a proposal, the new address will not be able to use the safe weight to vote on the same proposal. The new address will be able to vote on different proposals.
{% endhint %}







