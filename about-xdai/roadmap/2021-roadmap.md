# 2021 Roadmap

## 2021 Preliminary Roadmap

We will continue to add items and adjust priorities as the year continues. See the [2020 Roadmap](2020-roadmap-completed-items.md) for items completed in 2020.

_Last update: April 6, 2021 \|_ [_Changelog_](./#change-log)\_\_

{% hint style="warning" %}
The xDai project roadmap is a high-level strategic plan designed to guide xDai research and development. Target dates and details are reviewed regularly and subject to move, adjust and change as the project evolves. Note that only completed items \( ✅ Status: Complete\) are considered achieved project milestones.
{% endhint %}

![](../../.gitbook/assets/5-year-roadmap.png)

## EasyStaking, POSDAO and Liquidity Pool Analytics

🎯 **Target Date**: Q1 2021  
  **✅Status:** MVP Complete. Additions and improvements ongoing. 

* Dune Analytics [Staking Dashboard](https://www.duneanalytics.com/maxaleks/xdai-staking) \(includes EasyStaking & POSDAO; additional metrics ongoing\)
* LP [Distributions dashboard](https://stake-reward-distribution.xdaichain.com/)
* DappQuery [EasyStaking Dashboard](https://dappquery.com/dapp/easystaking-10047)

Analytics or EasyStaking rewards Liquidity Pool \(LP\) participants, stakers in the EasyStaking protocol and POSDAO stakers. [Rewards fluctuate based on numerous factors](../../for-stakers/easy-staking/#liquidity-pool-lp-participants), and additional analytics and dashboards for LPs will be useful for determining staking strategies, reviewing historical outcomes and viewing current statistics. 

We will integrate statistics views for the EasyStaking platform and POSDAO as well as develop additional analytics tools \(currently exploring options like Dune Analytics\). We will continue to add stats and views for stakers on all platforms.

## **xDai Grant Program** 

🎯 **Target Date:** Q2 2021  
☑ **Status:** In Process

Once the Ecosystem Fund unlock begins, we will finalize the program and begin accepting applications for developers and projects requiring support for wave 1 of the Grants Program.

## **Establish Bug Bounty for High Value Contracts**

🎯 **Target Date:** Q2 2021  
  **✅Status:** Program Established with [Immunefi](../../for-developers/immunefi-bug-bounty.md)

The first bounty is for OmniBridge contracts with a potential reward of $2,000,000 for critical bug discovery. We will continue to add additional bounties for other infrastructure including EasyStaking and POSDAO consensus contracts.

## **Improve STAKE Governance Processes**

🎯 **Target Date:** Q2 2021  
  **✅Status:** Improved [Snapshot Compatibility](https://snapshot.org/#/xdaistake.eth) with xDai, process optimizations ongoing. [More Details](../../for-users/governance.md)

STAKE is used for community signaling with [snapshot](https://snapshot.org/#/xdaistake.eth), and STAKE held on xDai is important for this process to reflect community sentiment. STAKE holders on xDai include POSDAO delegators and validators, perhaps the biggest supporters of the chain. There is a vital need to include these holders in the governance process. Snapshot compatibility will be expanded to include STAKE on xDai and STAKE currently staked in the POSDAO protocol. In addition, the governance process will be optimized to facilitate more community driven proposals and voting for the [Ecosystem Fund allocation](ecosystem-fund-roadmap.md).

## **Berlin HF activation and client updates**

🎯 **Target Date:** Q2 2021  
 ☑**Status:** Planned for mid-late April 2021

OpenEthereum is now running `3.2.2-rc.1-stable` and it includes the latest xDai POSDAO features. xDai validators will upgrade to the latest build, with several also migrating to the Nethermind client to support client diversity on xDai.  We plan to activate the Berlin hard fork shortly after it goes live on the Ethereum mainnet. The exact date is TBD but planned to be completed by the end of April.

## **Privacy Preserving Transactions**

🎯 **Target Date:** Q2-Q3 2021  
☑ **Status:** In process, defining requirements and exploring approaches

Implementation of additional zero-knowledge protocols and private transactions into xDai.

Since xDai is a stable token, the primary use of the chain is peer-to-peer payments. Just as with cash, privacy and anonymity should be an option when exchanging money or paying vendors for services. 

Currently, [Tornado.cash](https://tornado.cash/) is available to users to ensure Dai anonymity. Dai can be used with tornado.cash before and after bridging to xDai to ensure transaction anonymity.

We also plan to implement privacy preserving transactions on xDai directly. Additionally, we plan to enable privacy for STAKE transactions, allowing for anonymous staking on xDai and Ethereum.

We have invested in several [different approaches ](https://forum.poa.network/t/introducing-the-poa-zero-knowledge-fund/2698)to implement different ZK protocols into xDai based applications and wallets.

## Synthetic Assets on xDai based on UMA protocol

🎯 **Target Date**: Q2-Q3 2021  
☑ **Status:** In process. 50% implementation

UMA is a decentralized financial contracts platform built to enable Universal Market Access. Use UMA’s self-enforcing contract design patterns and provably honest oracle mechanism to create your own financial products using standards like ERC20

xDai will leverage UMA protocol to create derivatives on fiat currencies and enable them in supporting wallets. We currently have a reference implementation where sUSD can be transferred from the Ethereum Mainnet to the xDai chain and back. [sUSD example](https://docs.tokenbridge.net/eth-xdai-amb-bridge/susd-bridge-extension/transfer-susd-through-the-bridge-extension).

## OmniBridge Phase 2

🎯 **Target Date**: Q1-Q2 2021  
☑ **Status:** [Security Audit](../../for-developers/security-audits.md#tokenbridge-audit-by-quantstamp-covers-omnibridge) for Phase 2 in process.

Additional features will be added including bi-directional support \(ability to move tokens minted on xDai to Ethereum\) and additional decentralization mechanisms \(governance, additional validators, user-enabled signature execution\). 

## Universal NFT Bridge

🎯 **Target Date**: Q1-Q2 2021  
☑ **Status:** In process

An NFT bridge to allow users easy portability between xDai and Ethereum for all ERC721 tokens. This will improve interoperability and provide options for NFT minting and cross-chain transfers. _Update: Bridge is operational, UI is in development._  [_More information_](https://docs.tokenbridge.net/eth-xdai-amb-bridge/nft-omnibridge-extension)\_\_

## L2 scalability and composability for token transfers on xDai

🎯 **Target Date**: Q2 2021

We will research adopting other platforms such as Polkadot, Cosmos, Eth2 and [optimistic rollups](https://docs.ethhub.io/ethereum-roadmap/layer-2-scaling/optimistic_rollups/) deployed to xDai to implement a scalability solution on xDai. This will enable scaling of transfers \(up to 1000x\) for native tokens and synthetic tokens on top of xDai. 

## POSDAO Phase 3

🎯 **Target Date**: Q4 2021

A chain created specifically to leverage [POSDAO](../../for-validators/posdao-whitepaper.md), HoneyBadger BFT and Multi-Collateral DAI. This network will be designed from the ground up with our collaborative partners [LUKSO](https://www.lukso.network/) and [ARTIS](https://artis.eco/) to leverage [STAKE ](../../for-stakers/stake-token/)tokens and HBBFT consensus.

## Change Log

<table>
  <thead>
    <tr>
      <th style="text-align:left">Update</th>
      <th style="text-align:left">Items</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><em>06.04.2021</em>
      </td>
      <td style="text-align:left">
        <p></p>
        <ul>
          <li>Add Improve STAKE governance process</li>
          <li>Adjust target dates for synthetic assets &amp; private txs</li>
          <li>Add Berlin Hard Fork</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>18.03.2021</em>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Separate 2020 and 2021 Roadmaps to their own pages</li>
          <li>Added <a href="ecosystem-fund-roadmap.md">Ecosystem Fund Roadmap</a> as
            secondary page</li>
          <li>Add Bug Bounty Program</li>
          <li>Add Grants Program</li>
          <li>Update to NFT Bridge item</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>04.01.2021</em>
      </td>
      <td style="text-align:left">
        <p></p>
        <ul>
          <li>Organize 2020 items to completed, add preliminary 2021 Items</li>
          <li>Adjust target dates for some 2021 items</li>
          <li>Add NFT bridge</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

