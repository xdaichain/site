---
description: xDai & Matic scaling solutions
---

# Matic

As we compare chains, we see that xDai and Matic share several things in common: 

1. Both are Ethereum-based Proof-of-Stake \(PoS\) sidechains designed to address Ethereum mainnet issues like slow transactions, high fees, and throughput concerns. 
2. Both are completely compatible with Ethereum 1.0, meaning smart contracts, tokens, and other functionality can be ported over from Ethereum with very few changes, and run with more efficiency on a sidechain. 
3. Both are moving toward full decentralization and delegated staking.  

Although both chains fill similar roles as Ethereum scaling solutions, there are also some key differences separating the two. First we will show the basic parameters of each chain, then describe some of the [key differences](matic.md#key-differences).

## Parameters and features of each chain 

| Component | xDai | Matic |
| :--- | :--- | :--- |
| Mainet launch | October 2018 | May 31, 2020 |
| Compatibility with Ethereum | 100% | 100% |
| Staking Token | STAKE | MATIC |
| Transactional Token | xDai stable coin | MATIC volatile coin |
| Tx Stability | Stable | Volatile |
| Explorer | BlockScout: [https://blockscout.com/poa/xdai](https://blockscout.com/poa/xdai) | BlockScout: [https://explorer.matic.network/](https://explorer.matic.network/) |
| Sidechain Structure | EVM sidechain: 100% Ethereum patchset | Matic VM with More Viable Plasma |
| Block Times | 5 seconds, 70 TPS \(reported\) | 1 second, 7000 TPS \(reported\) |
| Asset withdrawal / Interoperability | TokenBridge BiDirectional transfers | Matic JS - 7 day withdrawal period from Matic -&gt; Ethereum |
| Sybil resistance | Phase 1: Proof-of-Stake with selected delegators Phase 2: Public delegated proof-of-stake | Phase 1: Proof-of-Stake with selected delegators Phase 2: Public delegated proof-of-stake |
| Consensus | AuRa, with roadmap to HBBFT | Peppermint \(a forked version of Tendermint BFT\) |
| Staking UI | Yes | Yes |
| Scalability | Horizontal \(Additional chains\) & Vertical \(node scaling\) | Horizontal \(additional chains\) |
| Real World Use Cases | Events, Conference Adoption, Burner Wallet | TBD Mainnet just launched |
| Meta-transactions \(abstracted gas fees\) | Yes | Yes |
| Validator / Delegator staking minimums | 20K STAKE Validator 1K STAKE Delegator | 1 MATIC for either |
| Staking token emission | 8,765,000 STAKE + max 15% yearly emission | 10,000,000,000 MATIC capped |
| Exchange based staking | Pre-staking at Bitmax: 36.4% APR | Binance Savings: 10% APR |
| Micro transactions | Supported, costs in stable currency allow for accurate resource planning | Supported, costs difficult to assess |
| Randomness | Contained within the protocol | Oracle based |
| Wallet support | Burner Wallet, Alpha Wallet, Nifty Wallet, Portis, Saturn, TrustWallet, Ledger, Trezor | Matic Wallet, Atomic Wallet, Trust Wallet, Ledger, Trezor |

## Key Differences

Under the hood, the PoS consensus process between the two chains is quite different. Matic uses a plasma-based framework with Tendermint BFT consensus to achieve very fast tx and block times. xDai uses POSDAO with Authority Round consensus.  

These different algorithms impact how each chain functions, but we will not go into the details here. Please see the links at the end of the article for more on the potential benefits and drawbacks of each.

Here we focus on key differences from a user perspective when interacting and or staking with Matic and xDai. 

1. **Stable chain vs volatile chain**: xDai is a stable chain, meaning transactions as well as fees are paid with a stable token \(xDai, which inherits the Dai peg to the US dollar\). On xDai, buyers and sellers know that transactions retain their value, and developers can plan for costs related to micro-transactions. On Matic, users can send stable currencies but fees are still paid with MATIC tokens, and tx costs are low but unpredictable. 
2. **Single Token vs Dual Token structure.** The Matic token is used for both transactions and as a staking/delegation token. Token prices, supply, and market forces impact chain transactions as well as the underlying Proof-of-Stake consensus. The xDai chain separates these concerns, with a stable transactional coin and market-driven staking coin. The STAKE staking token is a multi-chain staking token, and may be used for staking on other chains. 
3. **Asset transfers between chains:** Both chains are efficient wehn transferring assets from the Ethereum Mainnet, it takes a short amount of time to move ERC20 or ERC721 tokens from Ethereum to Matic or xDai.   However, moving assets back to the Ethereum Mainnet is a different story. On the xDai chain, assets can be moved in minutes to achieve very quick liquidity. With Matic, transactions must undergo a 7 day waiting period \(due to fraud checks\) before they are available on Ethereum.    Both chains also have allow for arbitrary messages \(data calls\) to pass between chains. With Matic messages can only be [transferred in a single direction  - from Ethereum to Matic](https://docs.matic.network/docs/develop/advanced/transfer-data). The Arbitrary Message Bridge on xDai allows for bi-directional message transfers and contract calls, creating additional interoperability.   
4. **Transactions Per Second \(TPS\) and Block Times**. Matic reports extremely fast times, 1 second blocks with 7000 TPS \(and theoretically up to 64,000 TPS\)! The xDai chain produces 5 second blocks with 70 transactions per second.   While xDai TPS is much faster than the Ethereum mainnet, there is still a wide gap between Matic and xDai. The slower tx times are not yet problematic on the xDai chain, but may be a concern in the future. To address this gap, xDai can scale horizontally \(by adding additional chains connected by bridges\) or vertically \(by optimizing nodes\). Because the POSDAO Proof of Stake algorithm allows for a configurable consensus, there are plans to move to HoneyBadger BFT consensus which will increase TPS by a factor of five. Additional research is being done around transaction prioritization, block parameter adjustment and other optimizations to make sure tx capacity and usage requirements are in alignment. 
5. **Staking**: Both chains offer validator and delegated staking opportunities as well as a UI for staking. However, the functionality and underlying processes differ. With Matic, validators and delegators can stake with just 1 Matic token. Validators take a % of any delegators commission, and the reward pool of 1.2 Billion Matic tokens is designed to support the network for 5 years. After that time, rewards will transition to tx fees. Validators are chosen based on stake amounts, and when they want to exit the protocol, must wait for 21 days before withdrawing their funds.  xDai validators must have 20,000 STAKE in order to declare node candidacy, and delegators must have 1,000 STAKE. This makes potential collusion much more costly for any malicious actors. Validators do not charge commission, but are guaranteed 30% of staking rewards. Reward emissions are created every year and are based on how much STAKE is staked into the protocol. Validators can submit a withdrawal claim during a staking epoch \(7 days\) and can withdraw their funds once the epoch is over.  Since misbehavior is accounted for during the staking epoch, there is no need to wait for 21 days to ensure there was no malicious activity.

### Links:

* What is Matic Network: [https://medium.com/matic-network/what-is-matic-network-466a2c493ae1](https://medium.com/matic-network/what-is-matic-network-466a2c493ae1)
* Matic FAQs: [https://docs.matic.network/docs/validate/faqs](https://docs.matic.network/docs/validate/faqs)
* Matic Validator Staking: [https://docs.matic.network/docs/validate/validator/introduction](https://docs.matic.network/docs/validate/validator/introduction)
* Matic Validator Requirements: [https://docs.matic.network/docs/validate/validator/responsibilities](https://docs.matic.network/docs/validate/validator/responsibilities)

