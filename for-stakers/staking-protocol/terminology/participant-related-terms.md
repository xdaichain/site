# Participant Related Terms

{% tabs %}
{% tab title="Participant" %}
* [Active Pool](participant-related-terms.md#active-pool)
* [Candidate ](participant-related-terms.md#candidate)
* [Candidate Pool ](participant-related-terms.md#candidate-pool)
* [Delegator ](participant-related-terms.md#delegator)
* [Initial Validators](participant-related-terms.md#initial-validators)
* [Inactive Pool](participant-related-terms.md#inactive-pool)
* [Validator ](participant-related-terms.md#validator)
* [Validator Pool ](participant-related-terms.md#validator-pool)
* [Validator Set](participant-related-terms.md#validator-set)
{% endtab %}
{% endtabs %}

### Active Pool

Active pools consist of all candidate and validator pools eligible to join the next staking epoch as members of the validator set. At the end of a staking epoch, the new validator set is constructed from this list. 

Active pools with higher stake have a higher likelihood of selection to the next epoch, but all active pools have a chance \(randomness introduces variation in selection\).

Random selection does not happen if there are 19 or fewer candidates/validators. If there are fewer than 20 candidates, every candidate becomes a validator.

To be considered active, a pool must contain at least the minimum stake amount \(currently 20K STAKE\) and be in good standing \(not banned\).

All active pools are listed in the active pools tab, arranged from highest stakes ratio to lowest stakes ratio. Delegators may add or move stake to and from active pools during a staking window. However, **if the active pool is a current validator, the change in stake amounts will not take effect until the next staking epoch**. 

An instant withdrawal from a validating pool is limited to the amount staked during the current staking epoch. However, any delegator in the validator’s pool \(including the validator themselves\) can order a withdrawal and remove their stake during subsequent staking epochs.

### Candidate

To become a validator and produce blocks on the chain, a participant must first declare themselves as a candidate.

To [become a candidate](../become-a-candidate-validator.md), a participant must:

1. Acquire both bridged STAKE and xDai tokens. This includes at least the minimum required candidate stake in STAKE and a small amount of xDai to process transactions. Recommended amounts: 20,000 STAKE tokens \(the current minimum required candidate stake\) and 1 xDai.
2. Configure and run a node that meets the technical requirements for the protocol. Once the node is functional, a participant can become a candidate by enabling a web3 wallet with their staking address, providing the mining address associated with their node, and staking the minimum required candidate stake.

Once added, candidates may attract delegators to stake into their pools, increasing the chances of the candidate’s selection to the next validator set.

When the next staking epoch begins, candidates are selected as validators based on the total amount of stake in their pool as well as a random number which provides some variation in the selection process \(if there are greater than 19 candidates\).

Candidates who are not selected remain in the active pool list, and can attempt to attract more stake to increase their selection chances in the next epoch if they choose to do so.

Every current validator can also be thought of as a potential candidate for the next validator set. Delegators can place stake on current active validators, and this pending delegation stake \(along with the previous placed stake\) will be considered during selection for the next staking epoch.

### Candidate Pool

The candidate pool is the total amount of STAKE currently placed on a candidate. This includes their own stake amount as well as any additional delegator’s stake. The larger the size of a candidate’s pool, the greater their odds of selection to the next validator set.

### Delegator

Delegators are participants who provide additional stake to protect the chain, but are not validators themselves. They do not need to run a node, and do not assume responsibility for consensus. To delegate, a participant must have both bridged STAKE and xDai, and place at least the minimum amount of delegator stake \(currently 200 STAKE, [can be changed through governance](../../../for-users/governance/stake-weighted-voting/)\) on a candidate pool. Delegators can place stake on multiple candidates, move stake from one candidate to another, or withdraw stake from candidates at any time.

Delegators place stake on candidates they believe will make good validators. Once a candidate becomes a validator, the delegator’s stake is activated and may not be withdrawn or removed during the current staking epoch. However, active stake can be ordered for withdrawal, and additional stake can be placed on an active validator \(within the staking window\) in anticipation of the next staking epoch.

Stake delegated to a validator accrues rewards for the delegator. While all validator pools within a validator set receive the same share of rewards, rewards within each pool are shared proportionally based on the amount of stake provided by the validator and the delegators. This may influence delegation strategies \(ie delegating to a smaller pool can increase reward amounts if that candidate is chosen as a validator\).

Pool rewards are proportionally distributed between a validator and the staking delegators, as long as the total delegators’ percentage of stake is below 70%. If the total delegators’ stake exceeds 70%, the delegators’ rewards are adjusted accordingly and the validator receives 30%.

If a validator is banned, any stake within the banned pool \(including delegated stake\) is frozen for a period of 90 days and can be withdrawn only when the ban is over. Delegators should perform due diligence when selecting candidates to stake on, and should think of their stake as a “vote” for that candidate to become a validator for the next staking epoch.

### Initial Validators

The protocol is designed to begin with a predefined set of nominated validators. After the first staking epoch, this validator set can change depending on the presence of additional candidates. The initial validator set for the xDai Stable Chain is comprised of the same [group of validators](../../../for-validators/about-xdai-validators/) responsible for securing the chain prior to the POSDAO upgrade.

### Inactive Pool

Inactive pools are candidate pools which do not meet the ‘active pool’ criteria. This includes banned validator pools and previous candidates/validators who do not meet the minimum stake requirements \(this can occur if funds are withdrawn or if a validator chooses to remove their pool\).

Underfunded pools are reactivated and moved to the active pools section once the minimum stake requirements are met \(their status is updated in the following block\).

To reactivate a banned pool after the 90 day ban is complete, a candidate must increase their stake by any amount as long as the total amount is equal to at least the minimum stake requirements. Adding stake calls the `stake` function and reinstates the pool.

### Validator

A validator is responsible for running a node that verifies transactions and finalizes blocks on the xDai chain. Validators are individuals or projects in the ecosystem that have the technical ability and desire to participate in the consensus process, and can provide the minimum amount of stake into their pool to participate. 

The initial group of validators for the first staking epoch is hard coded in the protocol. During the first staking epoch, additional entities may declare themselves as candidates and vie for additional validator slots \(see [becoming a candidate](../become-a-candidate-validator.md) for more information on this process\).

A validator serves the chain for one-week staking epochs as a member of the validator set. During this time, they participate in the consensus process \(including transaction verification, committing/revealing random numbers, and detecting/reporting malicious behavior\) and take turns proposing and sealing blocks. 

They receive block rewards as well as transaction and bridge fees in exchange for hosting a node, securing the chain and providing consensus on all transactions. Rewards are distributed according to the distribution rules of the protocol.

Validators may increase their stake amounts at any time by selecting their own pool in the list of pools and adding STAKE to that pool. This pending stake does not influence current rewards, but is used during the validator selection process for the next staking epoch.

Validators can also remove their pool from selection consideration to the next epoch with the Remove My Pool functionality. This button is active in the header for eligible pools.

### Validator Pool

The validator pool contains the total amount of STAKE placed on a validator \(including active and pending stake\). A snapshot of the the total amount of active stake is captured at the beginning of a staking epoch and used for reward distribution between the validator and its delegators at the end of the epoch. 

Additional pending stake may be placed on the validator pool during a staking epoch. This pending stake does not accumulate any rewards, but does influence the chances of the pool becoming a validator for the next staking epoch.

### Validator Set

The validator set is the current group of validators participating in consensus. The maximum number of validators in a set is 19, and a new validator set is chosen for each staking epoch. Members are selected based on the total amount of stake in their pool relative to the total deposited stake \(stake ratio\), along with a random number that adds variation to the process. A higher stake ratio results in a higher likelihood of selection, but it does not guarantee selection, as every active candidate has a chance to be selected to the next set.

If a validator in the set is removed for malicious behavior \(banned\), a new validator set containing the current set minus the malicious validator is installed into the protocol. This modified set containing 1 less validator completes the current staking epoch, and rewards are distributed equally among the modified set.

