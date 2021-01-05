# Public Staking \(Validators & Delegators\)

## How do I access the staking application?

The app is located in the xDai instance of BlockScout, available at [https://blockscout.com/poa/xdai](https://blockscout.com/poa/xdai). Go to the Apps dropdown and select either Validators, Active Pools, or Inactive Pools to access.

![](../../.gitbook/assets/validator-app.png)

Once you are in the DApp, connect your web3wallet \(like MetaMask\) to participate. [The Staking Operations section](../../for-stakers/staking-protocol/staking-operations/) details various actions you can take to Stake, claim rewards etc.

## What is a validator?

A validator runs a node that verifies transactions and finalizes blocks on the xDai chain. Each validator must provide the minimum STAKE collateral \(20K STAKE\) into their pool and setup a functional node to participate. They start as candidates, and have the chance to become validators each week when a new validator set is chosen.

## What is the maximum number of validators?

The max number of validators in a validator set is 19. This is called a validator set and is chosen each week from the group of validator candidates. 

## What is the maximum number of validator candidates?

The maximum number of candidates is 3000.

## How are validators selected?

If there are more than 19 suitable candidates, the top 19 are chosen based on the total amount of stake in their pool + a random number.

## What is a delegator?

A delegator is a STAKE holder who places STAKE in a validator candidates pool. If that candidate becomes a validator, the delegator also receives rewards. By placing STAKE, delegators vote on the candidates they think will make the best validators. 200 minimum delegation per validator candidate.

## How long is a staking epoch?

Each staking epoch is ~1 week \(120992 blocks\).

## How does a participant \(validator, candidate or delegator\) add/withdraw/claim STAKE?

A [UI integrated with BlockScout](https://blockscout.com/poa/xdai/validators) lets delegators and validators easily manage their STAKE tokens. For more info, see the [Staking Operations](../../for-stakers/staking-protocol/staking-operations/) section.

## How do I get my STAKE rewards as a validator/delegator?

Rewards are distributed at the end of a staking epoch to active validators and delegators. Participants must [claim their STAKE using the claim function](../../for-stakers/staking-protocol/staking-operations/claim-stake.md) to get rewards back to their wallet.

## How do I unstake/ stop delegating on a specific validator?

You will order a withdrawal for the **entire delegation amount**. At the end of the epoch, you will be removed as a delegator for that validator. See the question below for more details on the process.

## I ordered a withdrawal but don't see how to claim the withdrawal. What do I do?

You will need to wait until the staking epoch ends to claim your withdrawal. The claim functionality will be available at the beginning of the next epoch. Here are the general steps for withdrawing and claiming STAKE.

1. Order a withdrawal
   1. If you want to maintain your delegator status, be sure to leave at least 200 STAKE.
   2. If you want to remove yourself as a delegator, order the entire amount for withdrawal.
2. Wait until the staking epoch ends
3. After the epoch ends, a claim icon will appear. You will process this transaction and your ordered STAKE will be added to your wallet.

This page details the process along with a video tutorial. https://www.xdaichain.com/for-stakers/staking-protocol/staking-operations/claim-stake\#claim-ordered-withdrawals

## I don't see any icons to withdraw or add STAKE. Why not?

In all likelihood you are looking at the app during the final blocks of a staking epoch. During the last **4332 blocks** all staking actions are disallowed. This prevents any potential validator set manipulation at the end of an epoch. To prevent confusion, all staking-related icons \(withdraw, add, claim, move\) are temporarily removed from the UI. They will appear again once a new staking epoch begins.

## What rewards can I expect as a participant?

See the [rewards in a dual token environment post](../../for-stakers/stake-reward-mechanics/rewards-in-a-dual-token-environment.md) for more information. As a validator, you will always receive at least 30% of your pool's rewards, and more if delegators contribute less than 70% to the pool. Rewards are based on how much STAKE is staked in the protocol as well as chain-based activity \(stable rewards come from bridge fees and transactions\). Staking rewards will accumulate at 15% APR based on the locked amount.

## 

