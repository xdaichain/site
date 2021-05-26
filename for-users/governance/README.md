---
description: Community signaling with Snapshot and Forum proposals
---

# Governance

Community members can [create and vote on proposals ](https://forum.poa.network/c/xdai-chain/xdai-proposals/43)related to changes, improvements or anything they would like to see with the xDai ecosystem. Users can also add proposals related to [xDai Ecosystem Funds](../../about-xdai/roadmap/ecosystem-fund-roadmap.md) usage.  Voting is done with STAKE, and STAKE balances are retrieved from both Ethereum and xDai. STAKE in the following protocols can be used for voting purposes.

* Stake held either on Ethereum or xDai
* Stake staked in EasyStaking on Ethereum
* Delegated stake \(From a multisig wallet - [more info](stake-weighted-voting/delegate-stake-voting-weight-with-gnosis-safe.md)\)
* Stake on xDai protecting the chain in POSDAO \(validators and delegators\)

## **Standard Order of Events for Community Governance**

1. Forum Post in xDai Forum & Community Engagement
2. Snapshot voting proposal
3. Governance Board vote \(as appropriate\)

{% hint style="warning" %}
_Note: The process may be expedited when used by the xDai team to address infrastructure concerns or other time-sensitive issues._
{% endhint %}

### 1\) Forum post in proposals section of xDai forum

This is a first step to introduce your proposal and provide reasoning for why you are creating it and what benefits it will bring to the ecosystem. The community can voice their opinions and you can add more information about your proposal during and/or after the snapshot vote to clarify. A forum post should be shared with the community to allow for community comment.  
  
🔗 [Proposals Forum link](https://forum.poa.network/c/xdai-chain/xdai-proposals/43)  
⌚ Community feedback & discussion: 2 week suggested duration \(can be expedited when required\)  
☑ Proposals without any discussion/comments should not proceed to step 2. Try to engage the [telegram](https://t.me/xdaistable) and [discord](https://discord.gg/mPJ9zkq) communities for input and feedback.  


### 2\) Create a Snapshot Vote Proposal

This can be a simple proposal to assess community sentiment. It should reference your proposal in step 1. If there is not a need for faster resolution, set for at least 1 week to get community engagement.  
  
🔗 [xDai Snapshot Link](https://snapshot.org/#/xdaistake.eth)  
⌚ Voting Period: 1 week suggested duration \(can be expedited when required\)  
☑ Proposals that don't receive a yes vote, or are not engaged with will not be considered for the next step. Proposals that do see broad support will be considered for the governance board.  
 ⚖ [How to create and vote on a Snapshot Proposal with STAKE](stake-weighted-voting/)

### 3\) Forward Proposal Status for Governance Vote 

Reach out to the xDai team \(tag in your forum post or on [discord](https://discord.gg/mPJ9zkq)\) to let them know your proposal status. Depending on the nature and type of proposal the team will provide feedback and discuss internally regarding technical merits, ability to implement, internal priorities etc. If the proposal requires code modifications or changes to mechanisms requiring bridge signatures, it can be forwarded to the governance board \(see below\) for an inclusion vote.   
  
Results of the vote will be shared with the community once it is complete.

{% hint style="warning" %}
Proposals act as signaling events, but are never automatically enacted. Even if a proposal is popular in the community, snapshot/forum posts are suggestions and depending on technical requirements or other issues may not be enacted by the xDai technical team or bridge governors. If this is the case, reasoning will be discussed in the forum post \(step 1\).
{% endhint %}

## Governance Board

In response to increased usage and value locked in the xDai bridge, a proposal was introduced to extend security and decision making powers to a wider group of participants \(governors\).

The proposal was accepted, and governance by means of a multi-signature Gnosis Safe was put into place initially on the Ethereum side on 2 October, 2020. Once Gnosis Safe was deployed to xDai, updated governance was enacted on the xDai chain on 23 October, 2020.

At present there are 13 governors who are responsible for managing bridge operations on both sides of the bridge \(contracts are deployed on the Ethereum and xDai side\). 7/13 signatures are required to approve any management proposal. Operations may include:

* Bridge contract updates.
* Contract parameters updates such as bridge limits, finality threshold, gas price fallback etc.
* Bridge validator parameter updates like changing the validators set or signatures threshold.

All actions are managed through Gnosis Safe accounts, one on the Ethereum mainnet for Ethereum contract side operations and one on xDai for xDai contract operations.

* [Current xDai Bridge Governance Board Members](../../for-validators/for-bridge-validators/)
* Gnosis Safe contract on Ethereum: [https://gnosis-safe.io/app/\#/safes/0x42F38ec5A75acCEc50054671233dfAC9C0E7A3F6/settings](https://gnosis-safe.io/app/#/safes/0x42F38ec5A75acCEc50054671233dfAC9C0E7A3F6/settings)
* Gnosis Safe contract on xDai: [https://xdai.gnosis-safe.io/app/\#/safes/0x7a48Dac683DA91e4faa5aB13D91AB5fd170875bd/settings](https://xdai.gnosis-safe.io/app/#/safes/0x7a48Dac683DA91e4faa5aB13D91AB5fd170875bd/settings)

### Current Governing Board

{% hint style="info" %}
Several additional candidates are in review.
{% endhint %}

Requires 7/13 signatures to pass a proposal. Board is organized in a private telegram channel for discussion purposes. Results of any vote will be broadcast to the community.

* Gnosis
* Metacartel
* Request 
* RaidGuild
* Protofire 
* TokenBridge
* Lab10
* Burner Wallet
* Anyblock Analytics
* xDai Team
* Giveth
* Syncnode
* M Conti

