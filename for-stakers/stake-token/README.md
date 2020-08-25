# STAKE Governance and StakingToken

{% hint style="info" %}
STAKE is a flexible asset, meaning it may be used in a variety of contexts. The initial use case describes leveraging STAKE in the POSDAO implementation for xDai, however STAKE may be used for staking \(or other purposes\) by other blockchain networks. 
{% endhint %}

{% hint style="success" %}
STAKE token address on Ethereum [0x0Ae055097C6d159879521C384F1D2123D1f195e6](https://etherscan.io/token/0x0Ae055097C6d159879521C384F1D2123D1f195e6)
{% endhint %}

{% hint style="warning" %}
STAKE will protect the xDai consensus in phase 2 of POSDAO, **scheduled to begin in Q3 2020**. Details upcoming about how to stake on xDai as we approach that date. STAKE is available on the [BitMax exchange](https://bitmaxhelp.zendesk.com/hc/en-us/articles/360047308453-xDai-Chain-STAKE-) and coming soon to DEXs.
{% endhint %}

STAKE is a new ERC20-type \([implemented as an ERC677](https://github.com/ethereum/EIPs/issues/677)\) token designed to secure the on-chain payment layer and provide a mechanism for validators to receive multiple POS incentives. It is an ERC20-based staking token with a market driven value. 

The initial supply of 8.5375M STAKE tokens will be released over time. Additional tokens are minted as rewards at the conclusion of each staking epoch. 

Users \(stakers\) provide STAKE as collateral when participating in the consensus process. In exchange for providing STAKE \(and supporting a node\), users receive multiple rewards. The primary reward is in the form of additional STAKE tokens.

* **STAKE rewards**: STAKE is minted as a reward based on the amount of STAKE placed in the protocol. The final emission rate is TBD through a risk assessment and community review. Target range: ~15% APR.   A STAKE transfer fee is also assessed when a user removes their STAKE from the xDai chain \(using an [AMB bridge](https://docs.tokenbridge.net/amb-bridge/about-amb-bridge) extension\). This fee is distributed as a reward to participating stakers. 
* **xDAI rewards**: DAI locked in the bridge is converted to CHAI, which earns additional interest on the locked amount. This interest is distributed in xDai to stakers at the end of a staking epoch.

### Staking STAKE

When xDai public staking starts \(**scheduled for Q3 2020**\) , individuals who own STAKE tokens can place them into the protocol through a user friendly interface. Functionality includes an [AMB Bridge extension](https://docs.tokenbridge.net/amb-bridge/about-amb-bridge) which allows users to move STAKE tokens between the Ethereum mainnet and the xDai chain.

In addition, exchanges may offer the opportunity to provide delegator staking directly from the exchange. Typically, this means STAKE holders select the option to stake the token, and the exchange processes the request \(determining which validator to stake on, aggregating rewards and other tasks for a small percentage fee\). Staking functionality is initiated by the participating exchange. 

Validator candidates must meet certain requirements before placing STAKE \(the ability to run a functional node and minimum STAKE amounts\).  Delegators can place additional STAKE on candidates and receive rewards when the candidates they have placed STAKE on are chosen as validators.

When STAKE is locked in the protocol, rewards for sealing blocks are generated in STAKE and xDai. In addition, fees for removing STAKE from the xDai chain are assessed and distributed among active stakers.

### STAKE Total Supply 

The STAKE circulating supply is **8,537,500 tokens** \(once all tokens are unlocked in the protocol\).

 

