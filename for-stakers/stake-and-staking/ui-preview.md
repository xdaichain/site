---
description: Staking in BlockScout
---

# UI Preview

The xDai staking UI is currently under construction.  It will be incorporated directly into the [xDai block explorer BlockScout](https://blockscout.com/poa/xdai). This will provide users with the ability to easily stake, withdraw, move and claim STAKE and view transactions all from a single interface.  

## Video Sneak Peek

In 3 minutes we click through a few functions to give you a sense of the upcoming UI, including: 

* Tooltip Displays
* Claiming an Ordered Withdrawal \(Withdrawal was processed earlier, it is now available to claim\)
* Adding additional STAKE to a pool we are already delegating to
* Claiming an existing reward
* Viewing Delegators list and click on our account to see BlockScout Transactions
* Showing Candidate informational modal and Becoming a Candidate Modal
* Changing to light mode from night mode

{% hint style="info" %}
Block times, staking epochs, and staking amounts are all modified to enable faster testing iterations. Parameters will be updated in the live environment.

Transactions times were not altered, and take between 5-10 seconds for confirmation.
{% endhint %}

{% embed url="https://youtu.be/yoKl54HC7G8" caption="Quick visual run through of xDai Staking on BlockScout" %}

## Staking HOME Screen

Here you will find Epoch and Block number, as well as your account info in the top banner. You can also see the active validators along with how much they have staked. Click on the Delegators column to see a list of delegators.

![UI in BlockScout \(night mode\)](../../.gitbook/assets/home-screen-night-mode-tooltip.png)

## Delegators List

The delegators list includes address, current stake amount and reward percentages. The validator in the list has a checkmark, and if you are delegating you will see `ME` next to your name. Clicking on an address brings you to BlockScout to view transactions from that address.

![](../../.gitbook/assets/delegators-list.png)

## Placing Stake on a Delegator Modal

Just include the amount to place stake. It will not become active until the following staking epoch, assuming the candidate you staked on becomes a validator.

![](../../.gitbook/assets/place-stake.png)

## Claim Reward Modal \(light mode\)

You are able to claim rewards after every staking epoch you participated in. You can claim all, or specify a range to claim from.

![](../../.gitbook/assets/claim-reward.png)

{% hint style="info" %}
We will include more screens and a thorough run through of features as we get closer to the public POSDAO launch.
{% endhint %}

