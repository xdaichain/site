---
description: The EasyStaking application is in active development
---

# EasyStaking

{% hint style="warning" %}
This post describes a protocol-in-progress, parameters are being tuned and mechanisms are not yet finalized.  Mechanics and details are subject to change.
{% endhint %}

## EasyStaking

{% hint style="info" %}
See [EasyStaking Parameters](easy-staking-parameters.md) for basic application requirements and incentive details.
{% endhint %}

Easy Staking allows users to place STAKE into a contract and receive STAKE emissions on Ethereum. It provides an accessible staking mechanism for users and increases STAKE utility and DeFi composability. EasyStaking also:

* Incentivizes liquidity providers on decentralized exchanges through unique reward mechanisms
* Creates staking opportunities via hardware wallets and other Ethereum applications
* Provides staking opportunities with no minimum STAKE requirements to participate
* Limits total circulating supply

Total STAKE Emissions are minted at a total of 15% APR\*. Emissions are sent to stakers as well as Liquidity Pool Providers \(see below\) and provisioned to based on two parameters:

* **Time**: 7.5% APR. The amount of time STAKE has been committed to the protocol. Longer staking times result in a higher APR for the Staker.
* **Total Staked Amount**: 7.5% APR. The total amount in the pool from all Stakers and other contributors. Larger stakes result in a higher APR for all Stakers. More staked amount = higher rewards.

![Sigmoid function for determining time-based APR. The parameters a,b,c will be defined before App launching.](../../.gitbook/assets/sigmoid-1.png)

Stakers and Liquidity Providers each receive portions of the emission based on how long a Staker decides to keep STAKE in the application and the total amount Staked. Longer staking times benefit the Staker, and shorter staking periods benefit Liquidity Providers.

\*_Example APR. We are currently testing different emission models_

## Time-based Emission Example

| Example Staking Time | Staker | Liquidity Providers |
| :--- | :--- | :--- |
| 1 Month | 6.36% APR | 15 - 6.36 = 8.64% APR |
| 4 Months | 8.96% APR | 15 - 8.96 = 6.04% APR |
| 9 Months | 9.16% APR | 15 - 9.16 = 5.84% APR |

{% hint style="info" %}
As well as functioning as a stand-alone application, Easy Staking may be integrated into hardware wallets or other apps. We are exploring different use-cases.
{% endhint %}

## Liquidity Pool \(LP\) Participants

Liquidity pool providers will also receive STAKE incentives from the Easy Staking application. Users put funds into a Dai/STAKE liquidity pool on Uniswap will be eligible for these additional incentives.

 Here's an example of how it works for Bob:

1. Bob acquires 75 Dai and 30 STAKE by trading on [Uniswap](https://uniswap.exchange/swap), purchasing on [BitMax](https://bitmax.io/), or through some other means. \(Model assumes 75 Dai and 30 STAKE have equivalent value\) 
2. He goes to Uniswap \(v2\) and adds both into the STAKE/Dai liquidity pool. 
3. After some time, Bob checks his address and sees that he has received an additional 51 STAKE directly to his wallet. He has received STAKE rewards \(at a very high % relative to his pool contribution\) thanks to Mary withdrawing money from Easy Staking.

## STAKE distribution \(time-based only example\)

Mary has 10,000 STAKE she places into the Easy Staking application on the Ethereum Mainnet. She submits a deposit through the Easy Staking UI. After 1 year, she decides to realize her STAKE gains, and submits a withdrawal request. Assume APR is 10%. Since she deposited 10000 STAKE and staked for 1 year, Mary receives 11000 STAKE \(her initial amount + 10% APR\).  The remaining 500 STAKE \(5% APR\) earned as part of the total 15% APR are sent to the LP distribution contract.

Distribution to LP participants occurs through a script which collects addresses and pool amounts. It is called once each day \(within 24-hour time slots at random intervals\) and distributes funds based on pool participation percentages.

For simplicity, let's say only Bob and Roger were participating in the Uniswap LP. Bob has 75 Dai/30 STAKE and Roger has 25 Dai/10 STAKE in the pool when the distribution script is executed.  At this point, Bob receives 375 STAKE \(75% of the STAKE in the LP distribution contract\) and Roger 125 STAKE \(25%\) based on Mary's withdrawal scenario above.

In this example, this reward APR%  for Bob and Roger is very high, much more than they would have received for other staking methods, as they capture value from STAKE placed in the Easy Staking contract.  Distribution percentages will vary based on how much Dai exists in liquidity pools and how much STAKE is placed in the Easy Staking contract. 

## STAKE LP distribution script

Distributions to LP participants occur once within a 24-hour window at a random interval. This prevents any user from entering the liquidity pool at a predetermined time to receive STAKE distributions then exiting shortly thereafter.

The distribution script will run on a centralized server, and its results can be checked for bias or inaccuracy by any interested party. If the server is compromised, max losses are contained to 1 day of accrued interest from Easy Staking withdrawals. A multi-signature wallet will control Easy Staking parameters, including the address which calls distributions. If issues arise, this address may be changed through the multi-sig process.

Easy staking is non-custodial, no funds are collected and 100% of accumulated rewards are distributed to Easy Staking participants and LP participants.

More liquidity pools with different asset bases may be added in the future, and the distribution mechanics for these pools will be explored further.

## How to Participate

We will provide detailed instructions once the protocol is finalized.  We continue to refine the UI, and are starting to incorporate a calculator and a dynamic reward display.

