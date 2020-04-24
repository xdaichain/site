# Rewards in a Dual Token Environment

POSDAO is implemented on xDai with a dual token structure. 

1. **xDai** is the transactional stable coin, used for txs and fees.
2. **STAKE** is the volatile staking coin used to protect consensus.

To participate in POSDAO consensus, validator candidates must place 20K minimum STAKE to create a validator pool. Delegators may place additional STAKE \(1K minimum\) into any pool\(s\) they would like to support. Validator pools with a higher amount of STAKE have a higher probability of selection to the next validator set. 

While the amount of STAKE in a validator pool influences the chances of selection to a validator set, it **does not influence the reward amount a validator receives for sealing blocks**.

Within each pool, rewards are distributed based on the amount of STAKE contributed by delegators and the validator. Rewards are distributed based on the following rules:

1. Each pool in the validator set receives an equal share of the block reward on block creation.
2. Pool rewards are distributed proportionally, as long as the total delegator’s stake is below 70%.
3. The validator is guaranteed to receive at least 30% of the pool reward. If the total delegator’s stake exceeds 70%, the delegators’ rewards are adjusted accordingly.

![](../../.gitbook/assets/6-img.png)

Protocol rewards for validator pools come from multiple sources. Rewards accumulate based on actions that occur during a staking epoch, and are distributed at the end of the epoch to participating validators.

* **Transaction fees in xDai**: Sent to validator that seals the block containing the transactions.
* **STAKE rewards from sealing blocks**: STAKE placed in the protocol \(snapshot at the beginning of an epoch\) generates a 15% APR which is distributed to validator pools at the end of a staking epoch.
* **Bridge Fees \(STAKE & xDai\)**: Fees assessed when Dai is bridged to xDai, and when xDai is bridged to Dai. 
* **Chai interest \(xDai\)**: Dai placed in the protocol is locked as Chai, an interest bearing Dai derivative. Interest is distributed in xDai among validator pools.

