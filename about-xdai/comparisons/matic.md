---
description: xDai & Matic Ethereum Sidechains
---

# Matic Network

|  | xDai | Matic |
| :--- | :--- | :--- |
| 1: Chain Type | Stable Chain | Volatile Chain |
| 2: Token Structure | Dual token | Single Token |
| 3. Interoperability | xDai Bridge and OmniBridge | Plasma Bridge & PoS Bridge |
| 4. Staking | Staking Minimums, withdrawals after staking epoch | No staking minimums, 21 day waiting period for validator withdrawals |
| 5. Mainnet Launch | October 2018 | May 2020 |
| 6. Block Time/TPS | 5 second blocks, 70 TPS with future scaling ability to meet demand | 1 second blocks, 7000 TPS reported |
| 7. Total Value Locked | [Dynamic](https://defipulse.com/xdai) | [Dynamic](https://etherscan.io/address/0x40ec5b33f54e0e8a33a975908c5ba1c14e5bbbdf#tokentxns) |

_\*See below for more details. Comparison revised October 2020_ 

## Similarities & Differences

### Similarities

As we compare chains, we see that xDai and Matic share several things in common: 

1. Both are Ethereum-based Proof-of-Stake \(PoS\) sidechains designed to address Ethereum mainnet issues like slow transactions, high fees, and throughput concerns. 
2. Both are completely compatible with Ethereum 1.0, meaning smart contracts, tokens, and other functionality can be ported over from Ethereum with very few changes, and run with more efficiency on a sidechain. 
3. Both are moving toward full decentralization and delegated staking. 
4. Both chains incorporate 2 bridges for different use cases.

### Differences

Under the hood, the PoS consensus process between the two chains is quite different. Matic uses a plasma-based framework with Tendermint BFT consensus. xDai uses POSDAO with Authority Round consensus.  

These different algorithms impact how each chain functions, but we will not go into the details here. Please see the links at the end of the article for more on the potential benefits and drawbacks of each.

Here we focus on key differences from a user perspective when interacting and or staking with Matic and xDai. 

1. **Stable chain vs volatile chain**: xDai is a stable chain, meaning transactions as well as fees are paid with a stable token \(xDai, which inherits the Dai peg to the US dollar\). On xDai, buyers and sellers know that transactions retain their value, and developers can plan for costs related to micro-transactions. On Matic, users can send stable currencies but fees are still paid with MATIC tokens, and tx costs are low but unpredictable. 
2. **Single Token vs Dual Token structure.** The Matic token is used for both transactions and as a staking/delegation token. Token prices, supply, and market forces impact chain transaction prices as well as the underlying Proof-of-Stake consensus. The xDai chain separates these concerns, with a stable transactional coin and market-driven staking coin. The STAKE staking token is also a multi-chain staking token, and may be used for staking on other chains. 
3. **Asset transfers between chains:** Both chains are efficient when transferring assets from the Ethereum Mainnet, it takes a short amount of time to move ERC20 or ERC721 tokens from Ethereum to Matic or xDai.   In addition, both chains employ multiple bridges. Matic has recently introduced the[ PoS bridge](https://docs.matic.network/docs/develop/ethereum-matic/pos/getting-started) which provides faster transfers \(with lower security guarantees\) than the Plasma bridge, which requires a 7 day waiting period for withdrawals. The Matic POS bridge takes 10-30 mins to process a burn transaction. xDai transactions are typically finalized in 2-3 minutes.  xDai includes the xDai bridge for xDai &lt;-&gt; Dai transfers as well as the OmniBridge, where any ERC20 asset can be bridged immediately by anyone. While Matic's bridge also allows for asset transfers, users must request a specific asset be added to the setup through a mapping request. Both chains also allow for arbitrary messages \(data calls\) to pass between chains.   The xDai chain is currently researching an Optimistic OmniBridge model with plans to implement as an option for users in the near future. [More info is available here](https://ethresear.ch/t/optimistic-bridge-between-mainnet-and-a-pos-chain/7965).   
4. **Staking**: Both chains offer validator and delegated staking opportunities as well as a UI for staking. However, the functionality and underlying processes differ. With Matic, validators and delegators can stake with just 1 Matic token. Validators take a % of any delegators commission, and the reward pool of 1.2 Billion Matic tokens is designed to support the network for 5 years. After that time, rewards will transition to tx fees. Validators are chosen based on stake amounts, and when they want to exit the protocol, [must wait for 21 days before withdrawing their funds](https://docs.matic.network/docs/validate/validator/responsibilities).  xDai validators must have 20,000 STAKE in order to declare node candidacy, and delegators must have 200 STAKE. This makes potential collusion much more costly for any malicious actors. Validators do not charge commission, but are guaranteed 30% of staking rewards from their node. Reward emissions are created continuously as rewards and are based on how much STAKE is staked into the protocol. Validators can submit a withdrawal claim during a staking epoch \(7 days\) and can withdraw their funds once the epoch is over.  Since misbehavior is accounted for during the staking epoch, there is no need to wait for 21 days as with Matic to ensure there was no malicious activity. 
5. **Mainnet:** xDai has been in production since October 2018 and battle tested during that time. Security has been well tested in a live environment and xDai is a proven solution for scalability. Matic has been live since May of 2020, with less time in production and fewer deployed projects.  
6. **Transactions Per Second \(TPS\) and Block Times**. Matic processes 1 second blocks with a reported 7000 TPS \(and theoretically up to 65,000 TPS\). The xDai chain produces 5 second blocks with 70 transactions per second, which aligns with current transactional volume requirements. Gas limits purposefully match Ethereum block limits \(12.5M gas per block\), and as needs increase, xDai is built to scale with those requirements.  We believe in effective data and resource management where usage matches capacity, rather than an unnecessarily inflated TPS which can result in unmanageable state growth down the line.  xDai TPS is much faster than the Ethereum mainnet \(15-20 TPS\) and optimizations can be made to accommodate higher transaction rates as needed. The xDai chain is capable of scaling horizontally \(by adding additional chains connected by bridges\) or vertically \(by optimizing node requirements\).   Because the POSDAO Proof of Stake algorithm allows for a configurable consensus, there are plans to implement a HoneyBadger BFT consensus which will increase TPS by a factor of five. Additional research is being done around transaction prioritization, block parameter tuning and other optimizations to make sure tx capacity and usage requirements remain in alignment. We are also researching and applying state pruning techniques to ensure future data management capacity matches future usage.  ****
7. **Total Value Locked \(TVL\):** This is an ever changing proposition. Below we show ways to check the latest TVL.  **xDai:** The easiest way to find it on [BlockScout](https://blockscout.com/poa/xdai) where you can find the Marketcap. Hovering over the icon shows a breakdown of assets locked in the OmniBridge as well as Dai locked in the xDai Bridge. Below are contract which hold locked assets. xDai Bridge: [https://etherscan.io/address/0x4aa42145aa6ebf72e164c9bbc74fbd3788045016](https://etherscan.io/address/0x4aa42145aa6ebf72e164c9bbc74fbd3788045016) OmniBridge: [https://etherscan.io/address/0x88ad09518695c6c3712AC10a214bE5109a655671](https://etherscan.io/address/0x88ad09518695c6c3712AC10a214bE5109a655671)

![](../../.gitbook/assets/tvl.jpg)

  
**Matic:** Matic TVL can be viewed in their bridge contract address. The diversity of tokens in their ecosystem is lower, with stable coins \(like Tether and USDC\) making up a large proportion of value. [https://etherscan.io/address/0x40ec5b33f54e0e8a33a975908c5ba1c14e5bbbdf\#tokentxns](https://etherscan.io/address/0x40ec5b33f54e0e8a33a975908c5ba1c14e5bbbdf#tokentxns)

## Chain Parameters / Features 

<table>
  <thead>
    <tr>
      <th style="text-align:left">Component</th>
      <th style="text-align:left">xDai</th>
      <th style="text-align:left">Matic</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Mainet launch</td>
      <td style="text-align:left">October 2018</td>
      <td style="text-align:left">May 31, 2020</td>
    </tr>
    <tr>
      <td style="text-align:left">Compatibility with Ethereum</td>
      <td style="text-align:left">100%</td>
      <td style="text-align:left">100%</td>
    </tr>
    <tr>
      <td style="text-align:left">Staking Token</td>
      <td style="text-align:left">STAKE</td>
      <td style="text-align:left">MATIC</td>
    </tr>
    <tr>
      <td style="text-align:left">Transactional Token</td>
      <td style="text-align:left">xDai stable coin</td>
      <td style="text-align:left">MATIC volatile coin</td>
    </tr>
    <tr>
      <td style="text-align:left">Tx Stability</td>
      <td style="text-align:left">Stable</td>
      <td style="text-align:left">Volatile</td>
    </tr>
    <tr>
      <td style="text-align:left">Explorer</td>
      <td style="text-align:left">BlockScout: <a href="https://blockscout.com/poa/xdai">https://blockscout.com/poa/xdai</a>
      </td>
      <td style="text-align:left">BlockScout: <a href="https://explorer.matic.network/">https://explorer.matic.network/</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Sidechain Structure</td>
      <td style="text-align:left">EVM sidechain: 100% Ethereum patchset</td>
      <td style="text-align:left">Matic VM with More Viable Plasma</td>
    </tr>
    <tr>
      <td style="text-align:left">Block Times</td>
      <td style="text-align:left">5 seconds, 70 TPS (reported)</td>
      <td style="text-align:left">1 second, 7000 TPS (reported)</td>
    </tr>
    <tr>
      <td style="text-align:left">Asset withdrawal / Interoperability</td>
      <td style="text-align:left">TokenBridge BiDirectional transfers</td>
      <td style="text-align:left">
        <p>Matic PoS: fast withdrawals</p>
        <p>Matic Plasma: 7 day withdrawal period from Matic -&gt; Ethereum</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Sybil resistance</td>
      <td style="text-align:left">Phase 1: Proof-of-Stake with selected delegators
        <br />Phase 2: Public delegated proof-of-stake</td>
      <td style="text-align:left">Phase 1: Proof-of-Stake with selected delegators
        <br />Phase 2: Public delegated proof-of-stake</td>
    </tr>
    <tr>
      <td style="text-align:left">Consensus</td>
      <td style="text-align:left">AuRa, with roadmap to HBBFT</td>
      <td style="text-align:left">Peppermint (a forked version of Tendermint BFT)</td>
    </tr>
    <tr>
      <td style="text-align:left">Staking UI</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
    </tr>
    <tr>
      <td style="text-align:left">Client Support</td>
      <td style="text-align:left"><b>2 Client implementations</b> with
        <br />OpenEthereum &amp; Nethermind support xDai and POSDAO consensus</td>
      <td
      style="text-align:left">Single client built on top of <code>geth</code> using <code>bor</code> consensus
        mechanism.</td>
    </tr>
    <tr>
      <td style="text-align:left">Scalability</td>
      <td style="text-align:left">Horizontal (Additional chains) &amp; Vertical (node scaling)</td>
      <td style="text-align:left">Horizontal (additional chains)</td>
    </tr>
    <tr>
      <td style="text-align:left">Real World Use Cases</td>
      <td style="text-align:left"><a href="../project-spotlights/">Project List</a>
      </td>
      <td style="text-align:left">Project list: <a href="https://matic.network/dapps">https://matic.network/dapps</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Meta-transactions</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
    </tr>
    <tr>
      <td style="text-align:left">Validator / Delegator staking minimums</td>
      <td style="text-align:left">20K STAKE Validator
        <br />1K STAKE Delegator</td>
      <td style="text-align:left">1 MATIC for either</td>
    </tr>
    <tr>
      <td style="text-align:left">Staking token emission</td>
      <td style="text-align:left">8,765,000 STAKE + max 15% yearly emission</td>
      <td style="text-align:left">10,000,000,000 MATIC capped</td>
    </tr>
    <tr>
      <td style="text-align:left">Micro transactions</td>
      <td style="text-align:left">Supported, costs in stable currency allow for accurate resource planning</td>
      <td
      style="text-align:left">Supported, costs difficult to assess</td>
    </tr>
    <tr>
      <td style="text-align:left">Randomness</td>
      <td style="text-align:left">Contained within the protocol</td>
      <td style="text-align:left">Oracle based</td>
    </tr>
    <tr>
      <td style="text-align:left">Wallet support</td>
      <td style="text-align:left">Burner Wallet, Alpha Wallet, Nifty Wallet, Portis, Saturn, TrustWallet,
        Ledger, Trezor</td>
      <td style="text-align:left">Matic Wallet, Atomic Wallet, Trust Wallet, Ledger, Trezor</td>
    </tr>
  </tbody>
</table>

## Links:

* What is Matic Network: [https://medium.com/matic-network/what-is-matic-network-466a2c493ae1](https://medium.com/matic-network/what-is-matic-network-466a2c493ae1)
* Matic FAQs: [https://docs.matic.network/docs/validate/faqs](https://docs.matic.network/docs/validate/faqs)
* Matic Validator Staking: [https://docs.matic.network/docs/validate/validator/introduction](https://docs.matic.network/docs/validate/validator/introduction)
* Matic Validator Requirements: [https://docs.matic.network/docs/validate/validator/responsibilities](https://docs.matic.network/docs/validate/validator/responsibilities)

