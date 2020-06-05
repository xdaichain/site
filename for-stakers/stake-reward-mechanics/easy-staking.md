# Easy Staking

{% hint style="info" %}
This post describes a protocol-in-progress, parameters are being tuned and mechanisms are not yet finalized.  Expect changes to the final version.
{% endhint %}

## Easy Staking

Easy Staking allows users to place STAKE into a contract and receive STAKE emissions on the Ethereum Mainnet. It is an alternative to staking on the xDai chain - it does not protect consensus but does provide incentives for participants and limits the circulating STAKE supply.

Total STAKE Emissions are minted at 15% APR\*. The amount is divided between Stakers and Liquidity Pool Providers \(see below\). This division is determined by a formula whereby APR rises rapidly after a deposit is made then slows over time.  

APR formula parameters are available here: [https://www.desmos.com/calculator/wvy1eo9qzv](https://www.desmos.com/calculator/wvy1eo9qzv). By clicking on a point on the red curve you can view the month and approximate APR a STAKER will earn.

![](../../.gitbook/assets/sigmoid-1.png)

Stakers and Liquidity Providers each receive a portion of the emission based on how long a Staker decides to keep STAKE in the application. Longer staking times benefit the Staker, and shorter staking periods benefit wDai/STAKE Liquidity Providers. 

\*_Example APR. We are currently testing different emission models_

| Example Staking Time | Staker | Liquidity Providers |
| :--- | :--- | :--- |
| 1 Month | 2.69% APR | 12.31% APR |
| 4 Months | 8.85% APR | 6.15% APR |
| 9 Months | 12.81% APR | 2.19% APR |
| 14 Months | 13.97% APR | 1.03% APR |

{% hint style="info" %}
As well as functioning as a stand-alone application, Easy Staking may be integrated into hardware wallets or other apps. We are exploring different use-cases.
{% endhint %}

## Liquidity Pool Participants

Liquidity pool providers will also receive STAKE incentives as well as [Dai incentives](easy-staking.md#dai-distribution) from the Easy Staking application. Users put funds into a wDai \(wrapped Dai\)/STAKE liquidity pool on Uniswap will be eligible for these additional incentives.

 Here's how it works for Bob:

1. Bob trades 70 Dai for 70 wDai. This is a 1-to-1 trade on Uniswap or similar. 
2. Bob acquires 50 STAKE by trading on [Uniswap](https://uniswap.exchange/swap), purchasing on [BitMax](https://bitmax.io/), or through some other means. 
3. Bob now has STAKE and wDai.  He goes to Uniswap \(v2\) and adds both into the STAKE/wDai liquidity pool. 
4. After some time, Bob checks his address and sees that he has received an additional 6.97 STAKE directly to his wallet. He has received STAKE rewards \(at a very high %\) thanks to Mary withdrawing money from Easy Staking.

## STAKE distribution

Mary has 10,000 STAKE she places into the Easy Staking application on the Ethereum Mainnet. She submits a deposit through the Easy Staking UI. After 1 year, she decides to realize her STAKE gains, and submits a withdrawal request.  Since she deposited 10000 STAKE and staked for 1 year,  Mary receives 11365 STAKE \(Her initial amount + 13.65% APR\).  The remaining 135 STAKE \(1.35% APR\) earned as part of the total 15% APR are sent to the LP distribution contract.

At this point, the funds are not yet distributed. They remain and accumulate in this contract until a user \(Billy for example\) decides to press the `Distribute LP Funds` button and submits the transaction. Billy receives a small portion of the funds \(0.5% of the STAKE accumulated in the contract\) for initiating the distribution. 

When the button is pressed, LP funds are distributed to all wDai/STAKE Liquidity Pool participants \(ie Bob above\). Bob receives a portion of the 135 STAKE + any other STAKE in the fund based on how much wDai he has in the Liquidity Pool when the `Distribute` button is pressed. 

For simplicity, lets say Bob and Roger were the LPs, Bob had 70 wDai and Roger had 30 wDai in the pool when Billy presses the button. Bob receives 94.03 STAKE \(@70% of the STAKE in the distribution contract\) and Roger  40.29 STAKE \(@30%\) based on the withdrawal scenario above \(Billy the Button Pusher receives .68 STAKE!\). 

In this example, this reward APR%  for Bob and Roger is very high, much more than they would have received for other staking methods, as they capture value from all STAKE placed in the Easy Staking contract.  Distribution percentages will vary based on how much wDai is placed in liquidity pools and how much STAKE is placed in the Easy Staking contract. 

## STAKE distribution to LP participants

Hooks are added to the wDai token which provide on-chain information to the distribution contract.This allows for an easy formulation and distribution method to wDai/STAKE liquidity providers. STAKE is distributed to LP participants based on percentage amount a provider has in the liquidity pool on the block when the distribution call is made. 

## Dai distribution

When users convert wDai to Dai, there will be a small fee. This will also be sent to the LP contract, to be distributed to wDai/STAKE liquidity providers. 

More details will be provided as these mechanisms are developed.

## How to Participate

We will provide detailed instructions once the protocol is finalized. 

