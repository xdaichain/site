---
description: >-
  EXIT/STAKE liquidity pool providers will receive additional STAKE incentives
  from the Easy Staking application
---

# Liquidity Provider Program

The following describes a decentralized protocol where tokens are distributed through contract methods and initiated by users rather than any centralized structure.

{% hint style="info" %}
Parameters are being tuned and mechanisms are not yet finalized.  
{% endhint %}

## Liquidity Pool Participants

Users who place EXIT into the EXIT/STAKE liquidity pool on Uniswap will be eligible to receive additional STAKE rewards. Here's how it works for Bob:

1. Bob trades 7000 Dai for 7000 EXIT. This can be accomplished on [1inch.exchange](https://1inch.exchange/#/) or [curve.fi](https://www.curve.fi/) by exchanging Dai to EXIT.  The trade will be approximately 1:1, as EXIT and Dai are both stable tokens. 
2. Bob acquires 4000 STAKE by trading on [Uniswap](https://uniswap.exchange/swap), purchasing on [BitMax](https://bitmax.io/), or through some other means. 
3. Bob now has STAKE and EXIT.  He heads over to Uniswap \(v2\) and adds both into the STAKE/EXIT liquidity pool. 
4. After some time, Bob checks his address and sees that he has received an additional 6.97 STAKE directly to his wallet. He has received STAKE rewards for providing liquidity into the STAKE/EXIT pool, thanks to a Staker on the **Easy Staking** protocol!

## Easy Staking

Easy Staking allows users to place STAKE into a contract and receive STAKE  emissions on the Ethereum Mainnet. Emissions are minted at a 15% APR, but this amount is divided between Stakers and Liquidity Pool Participants. Each receives a portion based on how long STAKE remains in the Easy Staking contract. Longer commitment times benefit the Staker, and shorter commitments benefit EXIT/STAKE liquidity providers. 

| Time | Staker | Liquidity Providers |
| :--- | :--- | :--- |
| 0 -7 days | 5% APR | 10% APR |
| 8 - 84 days | 7% APR | 8% APR |
| 85 - 336 days | 10% APR | 5% APR |
| 337+ days | 14% APR | 1% APR |

## How it Works

Mary Staker has 10,000 STAKE she wants to place into the Easy Staking application on the Ethereum Mainnet. She submits a deposit through the UI. After 1 year, she decides to realize her STAKE gains, and submits a withdrawal request.  Since she deposited 10000 STAKE and staked for 1 year,  she receives 10140 STAKE.  The remaining 10 STAKE earned as part of the 15% APR is sent to the LP distribution contract.

At this point, the funds are not yet distributed. They remain and accumulate in this contract until a user \(Billy for example\) decides to press the `Distribute LP Funds` button and submit the transaction. Billy receives a small portion of the funds \(0.5% of the STAKE accumulated in the contract\) for initiating the distribution. When the button is pressed, LP funds are distributed to all EXIT/STAKE Liquidity Pool participants \(ie Bob above\). Bob receives a portion of the 10 Stake + any other STAKE in the fund based on how much EXIT he has in the Liquidity Pool when the `Distribute` button is pressed. 

For simplicity, lets say Bob and Roger were the LPs, Bob had 7000 EXIT and Roger had 3000 EXIT in the pool when Billy presses the button. Bob receives 6.97 STAKE and Roger 2.98 STAKE based on the withdrawal scenario above \(Billy the Button Pusher receives .05!\).

## STAKE distribution to LP Participants

Hooks are added to the EXIT token which provide information the distribution contracts can pull from the blockchain.This allows for an easy formulation and distribution method to EXIT/STAKE liquidity providers. STAKE is distributed based on the amount of EXIT in a liquidity pool on the block when the distribution call is made. More details will be provided when this mechanism is finalized.

## How to Participate

We will provide detailed instructions once the protocol is finalized. 







