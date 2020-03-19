# Protocol Related Terms

{% hint style="warning" %}
This page is a work in progress as implementation details are ongoing
{% endhint %}

{% tabs %}
{% tab title="Protocol " %}
* [Aura Algorithm](untitled.md#aura-algorithm)
* [Block/Bridge Rewards ](untitled.md#block-bridge-rewards)
* [Bridge ](untitled.md#bridge)
* [DPOS ](untitled.md#dpos-delegated-proof-of-stake)
* [Emission Curve ](untitled.md#emission-curve-emission-schedule)
* [Epoch ](untitled.md#epoch-staking-epoch)
* [Epoch Number ](untitled.md#epoch-number)
* [Fees](untitled.md#fees)
* [Hard Cap ](untitled.md#hard-cap)
* [Node ](untitled.md#node)
* [Reward distribution rules ](untitled.md#reward-distribution-rules)
* [Secret Number, Random number ](untitled.md#secret-number-randomness-beacon)
* [Stake token ](untitled.md#stake-token)
* [Technical Requirements ](untitled.md#technical-requirements)
* [Withdrawal Rules ](untitled.md#withdrawal-rules)
{% endtab %}
{% endtabs %}

### AuRa Algorithm

AuRa stands for Authority Round. It is the underlying algorithm currently used by the xDai chain to ensure validators produce blocks in an honest and timely fashion. In AuRa, validators take turns proposing blocks, and a majority of validators in the current active set must agree a block is valid before it is finalized. For more information, see [https://wiki.parity.io/Aura](https://wiki.parity.io/Aura)

There are plans to update the AuRa algorithm to Honey Badger BFT in future iterations of the xDai Stable Chain. More information on Honey Badger is available here [https://forum.poa.network/c/posdao/hbbft](https://forum.poa.network/c/posdao/hbbft)

### Block/Bridge rewards

Validators and their delegators receive rewards in exchange for securing the chain. Rewards are divided equally among each validator pool participating in the current staking epoch. At the end of each staking epoch, reward funds collected by validator pools are available for validators and delegators to claim. 

Within each pool, these rewards are further divided based on the reward.

{% hint style="info" %}
Details of the reward mechanism process are subject to change as we fine tune the model. 
{% endhint %}

Rewards take two forms; block and bridge rewards.

* Block rewards are allocated in STAKE, and sent to the validator pool \(validators & delegators\) responsible for creating and signing a block. Transaction fees in xDai are given to validators only \(not the validator pool\).
* Bridge rewards are collected whenever funds \(either xDai or STAKE\) are moved into or out of the chain. An entrance or exit fee is charged, and this fee is equally distributed to all validator pools in the validator set in place when the funds are bridged.

Reward funds collected by validator pools are distributed amongst the validator and the delegators according to the reward distribution rules at the end of each staking epoch.

![Configurable Reward Structure](../../../.gitbook/assets/block_bridge_rewards.png)

STAKE is the staking token, and xDai is the Native Coin. The 70/30 Split rules are detailed in the fees section.

### Bridge

A bridge uses the TokenBridge technology to connect two chains to one another, allowing for asset conversion from 1 chain to the other. The basic mechanism involves bridge smart contracts which locks assets on one side and mint them on the other. When the assets are moved back across the bridge, they are burned and unlocked. Bridges have their own set of validators which monitor token transfers.

![DPOS token is the STAKE token](../../../.gitbook/assets/bridge_1.png)

The xDai Stable Chain operates with two bridges:

1. An ERC20-to-Native Bridge converts DAI to xDai and vice versa. When Dai is “bridged”, the specified amount of DAI is locked in a contract and a corresponding amount of xDai is minted on the xDai Stable chain. During this minting process, a 1% fee is collected for validators \(ie. if 100 DAI are “bridged”, 99 xDai are transferred to the user’s wallet and 1 xDai is equally distributed amongst the current validator pools\). When converted back, a 1% exit fee is collected in the same manner. These fees are distributed at the end of a staking epoch.
2. An ERC20-to-ERC20 bridge converts STAKE ERC20 tokens on the Ethereum mainnet to STAKE on the xDai chain and vice versa. A 1% fee is also collected on entrance/exit and distributed to current validator pools.

**BRIDGE HOW TO NEEDED……**

Future bridge implementations will extend the multi-staking capability of the STAKE token, allowing additional sidechains to use STAKE  as a staking token via bridge connections.

![Additional chains connected by TokenBridge instances](../../../.gitbook/assets/bridge_2.png)

### DPOS \(Delegated Proof of Stake\)

Delegated Proof of Stake \(DPOS\) is an extension of Proof of Stake - a consensus model that provides rewards to validators in exchange for providing an amount of tokens as stake. This staking process incentivizes validators to act in the best interests of the network, as their stake will be impacted if malicious behavior is detected.

To increase the decentralization of this model and allow for wider community participation, the DPOS model allows any token holders to deposit stake. Delegators do this by placing stake on potential validators \(either current validators who may be elected to the next validator set, or candidates who are not currently validators\).

Delegators do not participate in block production themselves, but provide leverage to candidates they feel will make good validators. If these candidates are selected, rewards are divided amongst the validator and their delegators.

DPOS provides the opportunity for delegators to “vote” on potential validators by staking tokens on them. Candidates are incentivized to maintain a good reputation in order to attract more delegators and increase their chances of becoming validators. The POSDAO algorithm supports a DPOS model.

For more information on DPOS, see: [https://steemit.com/dpos/@dantheman/dpos-consensus-algorithm-this-missing-white-paper](https://steemit.com/dpos/@dantheman/dpos-consensus-algorithm-this-missing-white-paper)

### Emission Curve, Emission Schedule

The emission curve or schedule refers to the total amount of tokens that will be generated by a platform.

The STAKE token will be released according to a unique emission schedule.  For more information see: [STAKE  Token Rewards and Emission Model](https://forum.poa.network/t/dpos-staking-token-rewards-and-emission-model/2469)

xDai emission rates will not be determined by the protocol, as xDai correlates 1:1 with DAI, and the amount of xDai is always equal to the amount of DAI locked in the bridge smart contract.

### Epoch \(Staking Epoch\)

The time duration \(in blocks\) for which the validator set is selected. On the xDai Stable Chain AuRa implementation, each staking epoch lasts for 120954 blocks, which corresponds to a one-week timeframe with 5 second blocks. This value is configurable for other chains adopting the protocol.

### Epoch number

The number of the current staking epoch. The staking epoch increments every 120954 blocks on the xDai chain. A new validator set is chosen for each epoch.

### Fees

Fees are collected from users of the xDai chain and divided amongst validator pools. Fees are charged for bridge events and transactions.

* Bridge fees: A 1% fee is charged whenever tokens are locked or unlocked in a bridge contract. This entrance and exit fee is collected for both Dai &lt;-&gt; xDai transfers \(collected in xDai\) as well as STAKE \(mainnet\) &lt;-&gt; STAKE \(xDai chain\) transfers \(collected in STAKE\). Assessed bridge fees are split equally between validator pools active at the time of transfer.
* Transaction Fees \(Gas fees\): Transaction fees are assessed for any xDai transactions such as sending xDai to another wallet or interacting with a smart contract. These fees are sent to the validator who seals the block in which the transactions take place \(transaction fees are not split among pool participants, they are only received by the validator\). Transaction fees on the xDai chain are extremely low. As an example, during EthDenver over 38,000.00 of transactions were cumulatively charged less than .20 in transaction fees.

### Hard Cap

The STAKE token is subject to limited distribution, and the hard cap describes the maximum amount that will be released to various entities.  For additional information related to the release schedule, see [STAKE Staking Token Rewards and Emission Model](https://forum.poa.network/t/dpos-staking-token-rewards-and-emission-model/2469)

### Node

Candidates and validators are responsible for maintaining a node capable of verifying transactions and storing the entirety of the chain. A node must meet the technical requirements of the protocol. Instructions for setting up a node are available here .

### Reward distribution rules

Block rewards are shared by all validator pools participating in consensus. Rewards are distributed to validator pools according to the following rules:

1. Each pool in the validator set receives an equal share of the block reward on block creation.
2. Pool rewards are distributed proportionally, as long as the total delegator’s stake is below 70%.
3. The validator is guaranteed to receive at least 30% of the pool reward. If the total delegator’s stake exceeds 70%, the delegators’ rewards are adjusted accordingly.

Rewards are tallied and stored in a smart contract as each block is closed, and are distributed at the end of each staking epoch.

Detailed examples are available in the POSDAO whitepaper. [POSDAO white paper](https://forum.poa.network/t/posdao-white-paper/2208)

### Secret number, Randomness Beacon

The protocol implements a random number generator similar to ​RANDAO​, which is used to select a set of validators from the group of candidates at the start of each staking epoch. This number is used to add random variation to validator selection, although candidates with larger pools have a higher likelihood of selection to a validator set for each staking epoch \(candidates with higher stakes are probabilistically selected as validators for more staking epochs\).

This random number is generated by the current validator set during the staking epoch. Generation consists of several commits and reveal rounds, resulting in a cumulative process where entropy increases over the course of the epoch. If a validator skips revealing their secret number too often, or fails to reveal it in the last collection round \(which can influence selection for the next validator set\), they are treated as malicious and banned.

### STAKE token

STAKE is the staking token for the xDai Stable Chain. It is an ERC20 equivalent \(ERC677\) on the Ethereum mainnet, and an ERC20 equivalent \(ERC677\) when bridged to the xDai chain. STAKE is available in limited, hard-capped amounts in an initial public and private offering. It can be obtained through exchange listings… `more info here on where it is available, how to obtain`.

### Technical Requirements

In order to run a node, certain technical requirements should be met. More details are available here: &lt;link to xDai DPOS validator requirements/node setup post when created&gt;

Minimal system requirements:

* OS: Ubuntu Linux 16.04 LTS with root or sudo-user access over ssh
* CPU: minimum 2 cores
* RAM: minimum 4GB
* Disk: SSD
* Open network ports: SSH port \(default 22 TCP\), 30303 UDP. For security purposes, close other ports

Running 2 nodes simultaneously:

In addition, we recommend that each validator run two separate nodes simultaneously with different internet connections. This mitigates risk in the event a node goes down during the final reveal phase of a staking epoch. If this occurs, and there is no redundancy, the node is considered malicious and banned from the protocol.

To setup, the first node must have the ​engine\_signer​ option in a configuration toml file, the second node should not have that option but should have the ​watchguard​ script which​ detects if the first node goes offline and sets the ​engine\_signer​ option for the second node \(see [https://github.com/poanetwork/posdao-test-setup/issues/39](https://github.com/poanetwork/posdao-test-setup/issues/39)[​](https://github.com/poanetwork/posdao-test-setup/issues/39%E2%80%8B)\).

### Withdrawal Rules

Withdrawals are allowed during the open staking window.

* Any amount of stake including the entire stake amount \(minus any stake currently ordered for withdrawal and not yet claimed\) can be withdrawn from an active candidate during the staking window.
* Only stake placed in the current staking epoch may be withdrawn from a validator’s pool. An order for withdrawal can be placed on a validator’s pool; the ordered amount can be claimed during the next staking epochs.
* If an order for withdrawal has been placed, the amount can be changed during a staking epoch. To add an additional amount to withdraw, simply enter the additional amount. To withdraw a lower amount, enter a negative number to reduce the ordered amount. A transaction is created for each adjustment.
* Stake may be withdrawn during the staking window from an inactive validator, as long as that validator is not banned. If banned, the banned until date will show the date when stake may be withdrawn from the pool.

Ordered withdrawals can be claimed once the current staking epoch is complete \(within the staking window of any following staking epochs\).

