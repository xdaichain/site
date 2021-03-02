---
description: Current & Future Directions for the xDai Stable Chain
---

# Roadmap

{% hint style="warning" %}
The xDai roadmap is a high-level strategic plan designed to guide xDai research and development. Target dates and details are reviewed regularly and subject to move, adjust and change as the project evolves. Note that only completed items \( ✅ Status: Complete\) are considered achieved project milestones.
{% endhint %}

_Last update: 26.01.2021 \|_ [_Changelog_](./#change-log)\_\_

## ☑ 2021 Preliminary Roadmap

The roadmap for 2021 is still in review with additional items to be added and priorities adjusted as needed.

![](../../.gitbook/assets/5-year-roadmap.png)

## EasyStaking, POSDAO and Liquidity Pool Analytics

🎯 **Target Date**: Q1 2021  
  **✅Status:** MVP Complete. Additions and improvements ongoing. 

* Dune Analytics [Staking Dashboard](https://www.duneanalytics.com/maxaleks/xdai-staking) \(includes EasyStaking & POSDAO; additional metrics ongoing\)
* LP [Distributions dashboard](https://stake-reward-distribution.xdaichain.com/)
* DappQuery [EasyStaking Dashboard](https://dappquery.com/dapp/easystaking-10047)

Analytics or EasyStaking rewards Liquidity Pool \(LP\) participants, stakers in the EasyStaking protocol and POSDAO stakers. [Rewards fluctuate based on numerous factors](../../for-stakers/easy-staking/#liquidity-pool-lp-participants), and additional analytics and dashboards for LPs will be useful for determining staking strategies, reviewing historical outcomes and viewing current statistics. 

We will integrate statistics views for the EasyStaking platform and POSDAO as well as develop additional analytics tools \(currently exploring options like Dune Analytics\). We will continue to add stats and views for stakers on all platforms.

## **Privacy Preserving Transactions**

🎯 **Target Date:** Q2 2021  
☑ **Status:** In process, defining requirements and exploring approaches

Implementation of additional zero-knowledge protocols and private transactions into xDai.

Since xDai is a stable token, the primary use of the chain is peer-to-peer payments. Just as with cash, privacy and anonymity should be an option when exchanging money or paying vendors for services. 

Currently, [Tornado.cash](https://tornado.cash/) is available to users to ensure Dai anonymity. Dai can be used with tornado.cash before and after bridging to xDai to ensure transaction anonymity.

We also plan to implement privacy preserving transactions on xDai directly. Additionally, we plan to enable privacy for STAKE transactions, allowing for anonymous staking on xDai and Ethereum.

We have invested in several [different approaches ](https://forum.poa.network/t/introducing-the-poa-zero-knowledge-fund/2698)to implement different ZK protocols into xDai based applications and wallets.

## Synthetic Assets on xDai based on UMA protocol

🎯 **Target Date**: Q2 2021  
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

An NFT bridge to allow users easy portability between xDai and Ethereum for all ERC721 tokens. This will improve interoperability and provide options for NFT minting and cross-chain transfers.

## L2 scalability for token transfers on xDai

🎯 **Target Date**: Q2 2021

We will research adopting other platforms such as Polkadot, Cosmos, Eth2 and [optimistic rollups](https://docs.ethhub.io/ethereum-roadmap/layer-2-scaling/optimistic_rollups/) deployed to xDai to implement a scalability solution on xDai. This will enable scaling of transfers \(up to 1000x\) for native tokens and synthetic tokens on top of xDai. 

## POSDAO Phase 3

🎯 **Target Date**: Q4 2021

A chain created specifically to leverage [POSDAO](../../for-validators/posdao-whitepaper.md), HoneyBadger BFT and Multi-Collateral DAI. This network will be designed from the ground up with our collaborative partners [LUKSO](https://www.lukso.network/) and [ARTIS](https://artis.eco/) to leverage [STAKE ](../../for-stakers/stake-token/)tokens and HBBFT consensus.

## ✅ Completed 2020

## Fiat to xDai Onramp

\*\*\*\*🎯 **Target:** Q4 2019  
 ✅**Status:** [Ramp integration](../../for-users/get-xdai-tokens/buying-xdai-with-fiat/ramp-network.md) completed 2020. Includes support for 40+ countries, additional integrations and US support will continue to be explored

In order to offer options for users, xDai should be available for direct purchase. Prior to a fiat gateway, the primary method for users to get xDai is to get Dai first and relay it to xDai via the xDai Bridge. The process can be complicated and time-consuming due when Ethereum is congested.

The xDai team is working with payment processing companies to enable one or several Fiat to xDai onramps. 

## **Multi-Collateral Dai &lt;-&gt; xDai Bridge**

🎯 **Target Date:** Q4 2019  
✅**Status**: Complete. Summary: [https://forum.poa.network/t/migration-of-the-xdai-tokenbridge-completed/3212](https://forum.poa.network/t/migration-of-the-xdai-tokenbridge-completed/3212)

{% hint style="success" %}
xDai bridge is upgraded to support both Dai and Sai.

Bridge balance migrated from Sai to Dai. Both Dai and Sai can be deposited on the Ethereum side. Sai to Dai converted automatically.

_Update 4/15/2020: With the impending Sai shutdown, Sai transfers are no longer allowed on the bridge._ [_https://metamask.zendesk.com/hc/en-us/articles/360020394612-How-to-connect-a-Trezor-or-Ledger-Hardware-Wallet_](https://metamask.zendesk.com/hc/en-us/articles/360020394612-How-to-connect-a-Trezor-or-Ledger-Hardware-Wallet)\_\_
{% endhint %}

## Chai &lt;-&gt; Dai Bridge Contracts Update

🎯 **Target Date:** Q1 2020  
✅**Status**: Completed 03/31/2020

{% hint style="info" %}
This feature has been deprecated. The governing board may revisit at a later time or look to introduce another mechanism for incentivization.  
  
[Proposal and Decision](https://forum.poa.network/t/disable-chai-token-support-to-safe-gas-for-deposit-and-withdrawal-operations/3936)
{% endhint %}

{% hint style="success" %}
Bridge contracts are upgraded and functional. For more on _**`CHAI,`**_ see the [Chai FAQs](../../for-stakers/stake-token/stake-reward-mechanics/xdai-rewards/chai-faqs.md).
{% endhint %}

The new version of the bridge contract supports usage of [the Dai Savings Rate contract](https://community-development.makerdao.com/makerdao-mcd-faqs/faqs/dsr) through [the Chai token](https://chai.money/) to earn the interest for tokens deposited on the bridge balance. Dai locked in the bridge contract is converted to Chai, an interest earning form of Dai. The interest accumulated from the locked Chai during a staking epoch will be used as an additional incentive for stakers **in Phase 2** of the consensus upgrade. 

## Consensus POSDAO Upgrade: Phase 1

🎯 **Target Date:** Q1-Q2 2020  
✅**Status**: Completed 04/01/2020

{% hint style="success" %}
Phase 1 of the POSDAO upgrade was successfully activated April 1, 2020. 
{% endhint %}

xDai will upgrade to a Proof of Stake model in several phases. In the first phase, the current validators will receive xDai-based STAKE tokens and to protect the chain. These validators will remain in place to assist in the transition to phase 2.

For more information on this transition, see the [staking roadmap](../../for-stakers/stake-and-staking/).

## EasyStaking STAKE on Ethereum

🎯 **Target Date**: Q3 2020  
✅ **Status**: Completed 08/05/2020

[Easy Staking](../../for-stakers/easy-staking/) provides an alternative interest-earning application for [STAKE ](../../for-stakers/stake-token/)token holders. Users can deposit STAKE tokens deployed on the Ethereum mainnet and earn a pre-determined interest rate without bridging to xDai and with no minimum STAKE amount requirements. Rewards are split among Liquidity Providers and protocol stakers.

Easy Staking serves to reduce the overall amount of STAKE in active circulation and acts as a mechanism to limit available liquidity and supply. Limited supply in the open market increases security for POSDAO chains such as the xDai stable chain.

## OmniBridge Phase 1

🎯 **Target Date**: Q3 2020  
✅ **Status:** [Security Audits Completed 11/6/2020 ](../../for-developers/security-audits.md#tokenbridge-audit-by-quantstamp-covers-omnibridge)

Universal mediators will support transfers for virtually any ERC20 token to the xDai chain with no additional contract deployment. This lowers the barrier-to-entry for projects and DApps looking to move tokens to xDai and take advantage of low-fee, high-speed transactions. Users will be able to automatically create equivalent tokens on xDai ready for immediate usage.  Learn more here: [https://docs.tokenbridge.net/eth-xdai-amb-bridge/multi-token-extension](https://docs.tokenbridge.net/eth-xdai-amb-bridge/multi-token-extension)

## Bridge Governance Expansion

🎯 **Target Date:** Q3 2020  
✅ **Status:** [Completed for both sides of the bridge 10/23/2020](../faqs/bridges-xdai-bridge-and-omnibridge.md#what-is-the-bridge-governance-board).

Bridge management should be expanded to additional community representatives. These individuals will use a Gnosis Safe to manage bridge operations. A majority must sign to approve operations including:

* Bridge contracts upgrades
* Extending the set of bridge validators
* Updating bridge parameters like number of block confirmations, transactions limits,  bridge fees etc.

## Consensus POSDAO Upgrade: Phase **2**

🎯 **Target Date:** Q2 2021  
✅**Status:** Completed Q4 2020. 

To increase decentralization and enable a permissionless consensus process,  the broader community will have the opportunity to participate as validators and/or delegators in the consensus process. 

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
      <td style="text-align:left"><em>26.01.2021</em>
      </td>
      <td style="text-align:left">
        <p></p>
        <ul>
          <li>Update EasyStaking, POSDAO and Liquidity Pool Analytics to Complete</li>
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
    <tr>
      <td style="text-align:left"><em>23.12.2020</em>
      </td>
      <td style="text-align:left">
        <p></p>
        <ul>
          <li>Update POSDAO Phase 2 to completed.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>25.11.2020</em>
      </td>
      <td style="text-align:left">
        <p></p>
        <ul>
          <li>Update Fiat -&gt; xDai gateway status to completed.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>18.11.2020</em>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Update OmniBridge status to completed</li>
          <li>Update Bridge Governance status to completed</li>
          <li>Add OmniBridge Phase 2</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>24.09.2020</em>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Switch Fiat integration to Wyre</li>
          <li>Add Bridge Governance Expansion</li>
          <li>Revise public POSDAO targets from Q4 2020 to Q2 2021 to devote resources
            to <a href="https://ethresear.ch/t/optimistic-bridge-between-mainnet-and-a-pos-chain/7965">Optimistic Bridge development</a>.</li>
          <li>Add distributions dashboard to EasyStaking Liquidity Pool analytics</li>
          <li>Adjust order of items to reflect prioritization</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>06.08.2020</em>
      </td>
      <td style="text-align:left">
        <ul>
          <li>Update EasyStaking status to Completed</li>
          <li>Adjust POSDAO consensus upgrade target to Q4 2020</li>
          <li>Adjust Privacy Preserving transactions to Q3-Q4</li>
          <li>Added LP Analytics to Q3 2020</li>
          <li>Added Multi-Token Bridge to Q3 2020</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><em>28.05.2020</em>
      </td>
      <td style="text-align:left">
        <p>&lt;em&gt;&lt;/em&gt;</p>
        <ul>
          <li>Added EasyStaking Q3</li>
          <li>Updated Synthetic Assets to 50% complete</li>
          <li>Adjusted target date for L2 scalability to Q1 2021</li>
          <li>Renamed NG to POSDAO Phase 3, adjusted target date to Q2 2021</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

