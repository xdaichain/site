# Public Staking \(Validators & Delegators\)

## How do I access the staking application?

The app is located in the xDai instance of BlockScout, available at [https://blockscout.com/poa/xdai](https://blockscout.com/poa/xdai). Go to the Apps dropdown and select either Validators, Active Pools, or Inactive Pools to access.

![](../../.gitbook/assets/new-menu.png)

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

## What is an Inactive Pool?

A pool becomes inactive when a candidate/validator elects to stop participating in the consensus process. This is different from a ban, where a malicious validator is immediately removed from consensus.

If you see a current validator's pool status as inactive, the validator will exit the validator set once the current staking epoch is complete. Prior to the end of the epoch, the validator will continue with their responsibilities, and any delegators will receive rewards once the staking epoch is finished. Rewards may be diminished if the validator's participation was limited during that epoch.

Inactive pools are not considered for the next validator set, and will not become validators again unless the pool is reactivated by the validator.

## If I am a delegator on a validator pool that is inactivated, will I receive a reward? And how much?

Yes, rewards will still be distributed. If a pool is inactivated during a staking epoch, rewards for the current staking epoch will be accrued as usual.

The reward amount depends on how long the validator has been working during the staking epoch: the reward corresponds to the validator's participation in consensus during the staking epoch. 

For example, if the validator was working fine, didn’t disconnect their node, and produced all blocks they should have produced \(went through all AuRa rounds during the epoch\), its pool will receive 100% of the possible pool’s reward.

However, if the validator skipped half of the staking epoch \(only produced 50% of blocks they should have produced\), their pool will receive 50% of max possible pool’s reward. If a validator was malicious and was removed by the system for misbehavior, its pool won’t receive rewards. Pool rewards also depend on how much other participants staked into other pools. [Read more about reward distributions](../../for-stakers/staking-protocol/terminology/protocol-terms.md#reward-distribution-rules).

## Why did a pool become inactive, and who made the decision?

Pool inactivation is the pool validator's decision. They can inactivate themselves through the interface, or they may be inactivated if serious performance issues are not addressed. In the current implementation, a pool can be inactivated through a governance multisignature process in exceptional cases where there are too many block skips or if a node is too weak and works too slowly \(i.e. if the validator significantly degrades network performance\). This is only implemented if a deficient node significantly impacts chain stability. 

In the future a governance mechanism will enable validators to vote on the inactivation process and remove nodes that are negatively impacting chain performance. We plan to implement a monitoring tool which will provide insights into the performance of each validator pool. 

## What can I do if the pool I delegated to became inactive during a staking epoch?

Once the current staking epoch finishes, you can claim your reward and withdraw your staked amount \(or move the stake to another validator pool\). Due to POSDAO protocol rules, it is not possible withdraw STAKE immediately if a pool becomes inactive during a staking epoch. You must wait until a new epoch starts to move or withdraw your stake.

