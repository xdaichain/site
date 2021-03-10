---
description: For Staking and Governance
---

# STAKE Token

{% hint style="success" %}
STAKE token address on Ethereum [0x0Ae055097C6d159879521C384F1D2123D1f195e6](https://etherscan.io/token/0x0Ae055097C6d159879521C384F1D2123D1f195e6)

STAKE token address on xDai \(STAKE from Ethereum\)  
[0xb7D311E2Eb55F2f68a9440da38e7989210b9A05e](https://blockscout.com/xdai/mainnet/tokens/0xb7D311E2Eb55F2f68a9440da38e7989210b9A05e/token-transfers)
{% endhint %}

STAKE is a new ERC20-type \([implemented as an ERC677](https://github.com/ethereum/EIPs/issues/677)\) token designed to secure the on-chain payment layer and provide a mechanism for validators to receive multiple POS incentives. It is an ERC20-based staking token with a market driven value.

The initial supply of 8.5375M STAKE tokens will be released over time. Additional tokens are minted as rewards at the conclusion of each staking epoch.

Users \(stakers\) provide STAKE as collateral when participating in the consensus process. In exchange for providing STAKE \(and supporting a node\), users receive multiple rewards. The primary reward is in the form of additional STAKE tokens.

* **STAKE rewards**: STAKE is minted as a reward based on the amount of STAKE placed in the protocol. The final emission rate is TBD through a risk assessment and community review. Target range: ~15% APR.   A STAKE transfer fee is also assessed when a user removes their STAKE from the xDai chain \(using an [AMB bridge](https://docs.tokenbridge.net/amb-bridge/about-amb-bridge) extension\). This fee is distributed as a reward to participating stakers.

## Getting STAKE

There are [several ways to get STAKE](get-stake/) either on Ethereum or directly on xDai.

## Staking STAKE

Individuals who own STAKE tokens on xDai \(bridged from STAKE on Ethereum\) can place them into the protocol through a [user friendly interface on BlockScout](https://blockscout.com/xdai/mainnet/validators). Functionality includes an [AMB Bridge extension](https://docs.tokenbridge.net/amb-bridge/about-amb-bridge) with the [OmniBridge U](../../for-users/bridges/omnibridge.md)I which allows users to move STAKE tokens between the Ethereum mainnet and the xDai chain.

In addition, exchanges may offer the opportunity to provide delegator staking on Ethereum directly from the exchange. Typically, this means STAKE holders select the option to stake the token, and the exchange processes the request \(determining which validator to stake on, aggregating rewards and other tasks for a small percentage fee\). Staking functionality is initiated by the participating exchange.

Validator candidates must meet certain requirements before placing STAKE \(the ability to run a functional node and minimum STAKE amounts\). Delegators can place additional STAKE on candidates and receive rewards when the candidates they have placed STAKE on are chosen as validators.

When STAKE is locked in the protocol, rewards for sealing blocks are generated in STAKE and xDai. In addition, fees for removing STAKE from the xDai chain are assessed and distributed among active stakers.

## STAKE Total Supply

The STAKE circulating supply is **8,537,500 tokens** \(once all tokens are unlocked in the protocol\). Emissions will increase this value by a maximum of 15% annually.

## STAKE Governance

As the ecosystem matures, STAKE will be used for chain governance, giving holders a chance to update network parameters for optimal performance. This will include items such as validator/delegator minimums, fees, and other aspects of the xDai chain.

Community members can [submit governance proposals and vote with STAKE through Snapshot](stake-weighted-voting/).

In future iterations, holders will have the opportunity to use STAKE in a micro-governance context to determine things like transaction sequencing and priority on a per-block basis, giving a true community voice to the txs written directly to the chain. Value capture related to this concept, known as [Miner Extractable Value](https://ethresear.ch/t/mev-auction-auctioning-transaction-ordering-rights-as-a-solution-to-miner-extractable-value/6788), will give STAKE an intrinsic and important purpose when Eth 2.0 is ready for production.

{% hint style="info" %}
 STAKE is a flexible asset, meaning it may be used in a variety of contexts. The initial use case describes leveraging STAKE in the POSDAO implementation for xDai, however STAKE may be used for staking \(or other purposes\) by other blockchain networks.
{% endhint %}



