# Staking Rewards Comparison

There are several ways to earn STAKE staking rewards. Each method has tradeoffs, costs, and benefits. Your staking strategy can depend on the amount staked in each protocol, your desire to stay on Ethereum and moderate STAKE supply or to operate on xDai and directly protect the protocol, and risks including possibly losing rewards if your chosen validator is inactive.

Below is a basic breakdown of the different staking methods followed by an [example reward scenario](staking-rewards-comparison.md#example-reward-scenario).

## Staking Method Basics

|  | **EasyStaking** | **Liquidity Provider \(Uniswap\)** | **xDai Delegator** | **xDai Validator** |
| :--- | :--- | :--- | :--- | :--- |
| **Chain** | Ethereum | Ethereum | xDai | xDai |
| **Minimum staking requirement** | 0 | 0 | 200 STAKE\* \(\*subject to change\) | 20000 STAKE\* \(\*subject to change\) |
| **Withdrawals** | Instant \(with 2% fee\) or scheduled \(no fee\) | Instant | Instant if not active, ordered withdrawals if active | Instant if not active, ordered withdrawals if active |
| **Ethereum gas fees** | Deposit and Withdrawal costs | Deposit and Withdrawal costs | Costs to bridge STAKE from Eth -&gt; xDai | Costs to bridge STAKE from Eth -&gt; xDai |
| **Bridge fee rewards** | No | No | Possible | Possible |
| **xDai Tx rewards** | No | No | No | Yes |
| **Possible STAKE freeze?** | No | No | Possible 90 day freeze \(no withdrawal allowed or interest earned\)  if associated validator pool displays malicious behavior. | Possible 90 day freeze \(ban - no withdrawals allowed or interest earned\) if node displays malicious behavior \(too many skips, etc.\) |
| **Unique Benefits** | Easy, keep STAKE on Ethereum, reduces available supply. | LP rewards from Uniswap, large potential rewards from EasyStaking withdrawals. | Higher rewards, help decide xDai validators, can earn additional fee-based rewards. | Protect protocol, higher rewards, can earn additional fees. |
| **Unique Risks** | Ethereum fees,  contract risks, iff supply decreases rewards are lowered. | Impermanent loss, no rewards if not in top 100 pools. | New staking protocol, STAKE freeze possible, bridging costs, must order a withdrawal for active STAKE. | Large deposit, STAKE freeze for misbehavior, node maintenance and validator responsibilities. |

{% hint style="warning" %}
Staking carries inherent risk relative to expected rewards. [EasyStaking contracts are audited ](../../../for-developers/security-audits.md#easystaking-audit-by-quantstamp)and rewards are not dependent on validator actions. However, rewards are typically lower than with POSDAO. 

POSDAO rewards are generally ****higher, but depend on the validator's uptime and behavior. If a validator behaves correctly, rewards are higher. If not, rewards may be negligible along with possibility of frozen assets for a period of 90 days. 

**Weigh your comfort with possible risks with rewards when deciding your optimal staking strategy.**
{% endhint %}

## **Example Reward Scenario**

Let’s look at a possible staking scenario for each method in the first month of staking. We include assumptions that can impact earnings, so all of these results are approximate.  
  
We will not include fees as part of the rewards, but high gas fees on Ethereum will impact potential earnings as users must pay for deposits and withdrawals or bridging. 

###  **TLDR; Version**

{% hint style="info" %}
This is for **the first month of staking**. EasyStaking APR continues to increase on a Month-to-Month basis.
{% endhint %}

|  | **EasyStaking** | **Liquidity Provider \(Uniswap\)** | **xDai Delegator** | **xDai Validator** |
| :--- | :--- | :--- | :--- | :--- |
| **Amount Staked** | 1000 STAKE | 1000 STAKE \(also requires equivalent amount of ETH\) | 1000 STAKE | 20000 STAKE |
| **Time Staked: 1st Month** | 28 days | 28 days | 28 days | 28 days |
| **Supply in Protocol** | 1,342,000 STAKE | 150,000 STAKE | 400,000 STAKE | 400,000 STAKE |
| **Reward Earned\* \(does not include LP rewards, bridge fees, gas costs etc\)** | **5.87 STAKE** | **5.63 STAKE\***  _\(may increase if large withdrawal from EasyStaking\)_ | **12.5 STAKE** | **250 STAKE** |

### **Extended Version**

This table does not include the xDai Validator column. xDai Validator pool earnings in this scenario are equal to `Stake Earned per validator per month -  Delegator Amount Earned`.

|  | **EasyStaking** | **Liquidity Provider \(Uniswap\)** | **xDai Delegator** |
| :--- | :--- | :--- | :--- |
| **Amount** | 1000 STAKE | 1000 STAKE \(also requires equivalent amount of ETH\) | 1000 STAKE |
| **Time Staked** | 1 month | 1 month | 1 month |
| **Time-Based APR \(1st month of staking, APR continues to increase for EasyStakers as time increases\)** | 4.53% | 2.97% | 15% \(may be impacted by delegation percentage if &gt; 70%\) |
|  |  |  |  |
| **Supply in Protocol** | 1,342,000 STAKE | 150,000 STAKE | 400,000 STAKE |
| **MAX Supply** | 8,558,504 | 8,558,504 | 8,558,504 |
| **SupplyFactor** | 50% = 4,279,252 | N/A | N/A |
| **Supply-Based APR** | 3.13% | 4.37% | N/A |
|  |  |  |  |
| **Total APR** | 7.66% | 7.34% | 15% |
|  |  |  |  |
| **Number of Validators** | N/A | N/A | 19 |
| **Validator Earnings per epoch \(weekly\)** | N/A | N/A  | totalStakeAmount \* 15/4800 = 1250 per week |
| **Number of Epochs in 1 Month** | N/A | N/A | 4 |
| **Stake Earned per validator per month \(active all 4 months\)** | N/A | N/A | 5000/19 = 263.15 |
| **Percentage in Pool with 1 delegator and minimum amounts staked** |  |  | 1000/21000 = 4.76% |
|  |  |  |  |
| **Total Earned Formula** | `1000 * .0766 / 365 * 28`  | `1000 * .0734 / 365 * 28`  | `263.15 * .0476` |
| **Total Earned\* \(does not include LP rewards, bridge fees, gas costs etc\)** | **5.87 STAKE** | **5.63 STAKE** | **12.5 STAKE** |

{% hint style="info" %}
For a quick estimate for Easy Staking or LP rewards, see the staking rewards calculator at [https://www.stakingrewards.com/earn/xdai/calculate](https://www.stakingrewards.com/earn/xdai/calculate)  or use the calculator directly at https://easy-staking.xdaichain.com/.
{% endhint %}

