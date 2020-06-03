---
description: >-
  EXIT/STAKE liquidity pool providers will receive additional STAKE incentives
  from the Easy Staking application
---

# Liquidity Provider Program

{% hint style="info" %}
This post describes a protocol-in-progress, parameters are being tuned and mechanisms are not yet finalized.  Expect changes to the final version.
{% endhint %}

## Liquidity Pool Participants

Users who place EXIT into the EXIT/STAKE liquidity pool on Uniswap will be eligible to receive additional STAKE rewards. Here's how it works for Bob:

1. Bob trades 70 Dai for 70 EXIT. This can be accomplished on [1inch.exchange](https://1inch.exchange/#/) or [curve.fi](https://www.curve.fi/) by exchanging Dai to EXIT.  The trade is approximately 1:1, as EXIT and Dai are both stable tokens. 
2. Bob acquires 50 STAKE by trading on [Uniswap](https://uniswap.exchange/swap), purchasing on [BitMax](https://bitmax.io/), or through some other means. 
3. Bob now has STAKE and EXIT.  He heads over to Uniswap \(v2\) and adds both into the STAKE/EXIT liquidity pool. 
4. After some time, Bob checks his address and sees that he has received an additional 6.97 STAKE directly to his wallet. He has received STAKE rewards \(at a very high %\) thanks to a second applications -  **Easy Staking**!

## Easy Staking

Easy Staking allows users to place STAKE into a contract and receive STAKE  emissions on the Ethereum Mainnet. It is an alternative to staking on the xDai chain - it does not protect consensus but it does provide incentives for participants and limits the circulating STAKE supply.

STAKE Emissions are minted at 15% APR, and the amount is divided between Stakers and Liquidity Pool Participants. Each receives a portion based on how long a Staker decides to keep STAKE in the application. Longer staking times benefit the Staker, and shorter staking periods benefit EXIT/STAKE Liquidity Providers. 

| Staking Time | Staker | Liquidity Providers |
| :--- | :--- | :--- |
| 0 -7 days | 5% APR | 10% APR |
| 8 - 84 days | 7% APR | 8% APR |
| 85 - 336 days | 10% APR | 5% APR |
| 337+ days | 14% APR | 1% APR |

## STAKE distribution

Mary has 10,000 STAKE she wants to place into the Easy Staking application on the Ethereum Mainnet. She submits a deposit through the Easy Staking UI. After 1 year, she decides to realize her STAKE gains, and submits a withdrawal request.  Since she deposited 10000 STAKE and staked for 1 year,  Mary receives 10140 STAKE \(Her initial amount + 14% APR\).  The remaining 10 STAKE \(1% APR\) earned as part of the total 15% APR are sent to the LP distribution contract.

At this point, the funds are not yet distributed. They remain and accumulate in this contract until a user \(Billy for example\) decides to press the `Distribute LP Funds` button and submit the transaction. Billy receives a small portion of the funds \(0.5% of the STAKE accumulated in the contract\) for initiating the distribution. 

When the button is pressed, LP funds are distributed to all EXIT/STAKE Liquidity Pool participants \(ie Bob above\). Bob receives a portion of the 10 STAKE + any other STAKE in the fund based on how much EXIT he has in the Liquidity Pool when the `Distribute` button is pressed. 

For simplicity, lets say Bob and Roger were the LPs, Bob had 70 EXIT and Roger had 30 EXIT in the pool when Billy presses the button. Bob receives 6.97 STAKE \(70% of the 10 STAKE in the distribution contract\) and Roger 2.98 STAKE \(30%\) based on the withdrawal scenario above \(Billy the Button Pusher receives .05!\). 

In this example, this reward APR% is much higher than Bob and Roger would have received for other staking methods, as they capture value from all STAKE placed in the Easy Staking contract. As the program evolves, distribution percentages will vary based on how much EXIT is placed in liquidity pools and how much STAKE is placed in the Easy Staking contract. 

## STAKE distribution to LP Participants

Hooks are added to the EXIT token which provide on-chain information to the distribution contract.This allows for an easy formulation and distribution method to EXIT/STAKE liquidity providers. STAKE is distributed based on the amount of EXIT in a liquidity pool on the block when the distribution call is made. More details will be provided as this mechanism is developed.

## How to Participate

We will provide detailed instructions once the protocol is finalized. 







