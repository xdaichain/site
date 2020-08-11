# EasyStaking FAQ

## Participation Questions

### How do I stake STAKE?

There are currently 2 ways to add STAKE to the EasyStaking protocol.

1. Go to [https://easy-staking.xdaichain.com/](https://easy-staking.xdaichain.com/) and connect your web3wallet. [More instructions](instructions.md).
2. Stake through BitMax. [More instructions](https://bitmax.io/#/staking/investment-product-details/STAKE-S).

### How do I unstake STAKE?

With the EasyStaking application you can withdraw your full amount to unstake. You can do this instantly and pay a 2% fee, or schedule a withdrawal and withdraw after 12 hours. [Instructions](instructions.md#initiate-a-withdrawal).

If you are staking with Bitmax, you can undelegate instantly for a 2% fee, or schedule a withdrawal and withdraw after 24 hours.  [More information](https://bitmax.io/#/staking/investment-product-details/STAKE-S).

### How much STAKE is in the EasyStaking Contract?

You can view the contract here:  [https://etherscan.io/address/0xecbcd6d7264e3c9eac24c7130ed3cd2b38f5a7ad](https://etherscan.io/address/0xecbcd6d7264e3c9eac24c7130ed3cd2b38f5a7ad) Look under the token dropdown to see the current amount in the contract.  

For context, you can compare this to the circulating supply, which is available on CoinGecko, CMC, or here:  [https://supply.xdaichain.com/](https://supply.xdaichain.com/)

### How do I participate as a Liquidity Provider \(LP\)?

Simply add STAKE and ETH to the following Uniswap pool. [https://uniswap.info/pair/0x3B3d4EeFDc603b232907a7f3d0Ed1Eea5C62b5f7](https://uniswap.info/pair/0x3B3d4EeFDc603b232907a7f3d0Ed1Eea5C62b5f7)

You will receive rewards based on the [LP distribution contract](./#stake-lp-distribution-script).

### I was staking on BitMax during the promotional period. Do I need to do anything to start EasyStaking?

No, your funds will be automatically moved to delegate on EasyStaking through Bitmax. You don't need to do anything if this is your preference. If you want to move your funds, you can undelegate through BitMax then send to an address you can access with MetaMask/NiftyWallet to use EasyStaking with your own address.

Note: Moving funds and staking independently will incur gas fees.

### What are the differences between staking independently through EasyStaking and staking through BitMax?

Both use the EasyStaking system, but rules are slightly different. More Bitmax rules are available here: [https://bitmaxhelp.zendesk.com/hc/en-us/articles/360052047914](https://bitmaxhelp.zendesk.com/hc/en-us/articles/360052047914)

|  | Independent | With BitMax |
| :--- | :--- | :--- |
| Minimum STAKE | .000000000000000001 | 10 |
| Minimum Unstake amount | .000000000000000001 | 10 |
| Reward Calculation | Immediate | T + 1 Day |
| Reward Distribution | Immediate | T + 2 Day |
| Distribution Cycle | On Demand | Daily |
| Withdrawal | Instant / 12 hour scheduled  | Instant / 24 hour scheduled |
| Instant Withdrawal fee | 2% | 2% |

## APR Questions

### How is APR calculated for EasyStaking?

APR is calculate in 2 ways, each with a maximum 7.5% for the EasyStaking staker. \(totaling a max of 15%\). 

In the following example, the time based emission after 10.2 days is  @2.011 APR, and the Supply based emission with 1.25M STAKE staked is @2.196. This results in a \(2.011 + 2.196 = 4.207\) @4.207% APR if a withdrawal is processed at this time. 

1\) **Time based**: Emissions are earned based on the amount of time in the protocol. These rise quickly and then level off, based on a [sigmoid function](https://www.desmos.com/calculator/2xtimbnzqw).  

If you click on a timepoint on the sigmoid graph you will see the number of seconds corresponding to the APR. In this example, the \# of seconds is 880,000 \(10.18 days\) and APR is 2.011%.

![Click on the line to see the APR based on \# of seconds staked](../../.gitbook/assets/sigmoid%20%281%29.png)

2\) **Supply based:** APR based on the total supply. The total supply can also be adjusted using the `totalSupplyFactor` parameter \(currently set to 50%\). If the supply in the contract is 1.25M and the total supply is set to 4,268,752.50, then the Supply APR is `1,250,000/4,268,752.5 * 7.5` or 2.196%

### I am staking for {1 day, 1 week, 1 month etc } how much APR will I earn?

We can find this out from the [sigmoid function](https://www.desmos.com/calculator/2xtimbnzqw) by converting the time to seconds.  Here are some approximate conversions:

* 1 day: 86400 seconds \(8.64\*10^4\)  = .19%
* 1 Week 604,800 seconds \(6.04\*10^5\) = 1.4% 
* 1 Month 2419200 seconds \(2.41\*10^6\) = 4.53% 
* 2 `M`onths: 4838400 seconds. \(4.83 \*10^6\) = 6.25%

This APR is then added to the supply based APR to get total APR on withdrawal. Supply APR is linear and can be found with the following formula:   
  
`Stake in EasyStaking Contract / (Total STAKE Supply * supplyFactor(.5))  * 7.5`

### How is APR calculated for Liquidity Providers \(LP\)

Liquidity providers receive `15 - ( EasyStaking time APR + EasyStaking supply APR)` .  

So for example, if a staker withdraws with a 2.011% time APR and a 2.196% supply APR, the LP contract will receive 15 - \(2.011 + 2.196\) = 10.793%.  This amount will be split amongst the LP providers based on how much STAKE they have in the LP contract. 

LP providers also split the 2% instant withdrawal/unbonding fee.

Rewards to LPs are distributed based on the [LP distribution script](./#stake-lp-distribution-script).

### I heard I will earn 15% APR. Why is it lower than that?

15% is the total emissions earned on all STAKE staked in the contract and is divided amongst stakers and Liquidity Providers.  If a participant stakes for a long time and the supply in the contract relative to total supply is very high, the APR for this individual may approach this amount, but will likely never reach the full 15% due to the sigmoid function and supply limits. 

### What is the predicted APR over time?

It will fluctuate based on the amount in the contract and how long you have staked. See the questions above for answers on how APR is derived for stakers and for liquidity providers.

### Why did APR drop from 36.4% to less than 1% on BitMax?

The 36.4% APR was part of a 3 month promotional program called Stake Vault. This was designed for 3 months \(effectively meaning it was a 9% APR if spread over the course of a year\). 

Now that StakeVault is done, Bitmax is moving funds to EasyStaking with some slight variations on how it is used. The APR on the BitMax staking page will update daily and adjust to reflect the amount of time STAKE has been in the protocol.

### Will I make more APR as an LP \(Liquidity Provider with Uniswap\) or as a staker with EasyStaking?

We will see - it depends on how the game is played! In general, if not much supply is staked and stakers unstake quickly, Liquidity Providers will prevail. However, if stakers stake for a long time, and the supply in EasyStaking continues to grow, stakers will earn more.

APR earnings may also depend on timing for liquidity providers. If a large staker cashes out, the remaining APR \(15 - staker APR\) will go to all LPs, regardless of how long they have been an LP. If an LP starts right before a big unstaking event, they may earn a considerable amount of STAKE.

From a risk management perspective, Easy Staking involves a single token rather than multiple tokens, and the contracts have been thoroughly audited. 

So the answer is "it depends", and we will see how it plays out in practice.

