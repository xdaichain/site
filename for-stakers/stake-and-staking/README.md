---
description: POSDAO enables staking on the xDai chain
---

# POSDAO Staking Roadmap

The xDai Chain is transitioning to POSDAO, a Proof of Stake consensus protocol. POSDAO will introduce a staking token called STAKE. Individuals who own STAKE may become validators or may delegate their stake to validator candidates to secure the xDai chain. Validators and delegators \(stakers\) will receive rewards in exchange for providing STAKE.

The transition to POSDAO will proceed in phases. Phase 1 of this transition was completed on **April 1, 2020**. Below are details related to the transition & what to expect in each phase.

{% hint style="info" %}
For general information, see the [Staking Protocol ](../staking-protocol/)for details on how to stake, protocol terminology, and more. 

For more on POSDAO, see the [POSDAO Whitepaper](../../for-validators/posdao-whitepaper.md)

For more on the STAKE token, see [https://www.staketoken.net/](https://www.staketoken.net/)
{% endhint %}

<table>
  <thead>
    <tr>
      <th style="text-align:left">Phase</th>
      <th style="text-align:left">General</th>
      <th style="text-align:left">Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">1) <a href="./#phase-1-preparation-and-permissioned-posdao">Preparation and Permissioned POSDAO</a>
      </td>
      <td style="text-align:left">POSDAO transition for current xDai validators only</td>
      <td style="text-align:left">Completed:
        <br />04/01/2020</td>
    </tr>
    <tr>
      <td style="text-align:left">2) <a href="./#phase-2-public-staking-and-reward-expansion">EasyStaking, Public Staking &amp; Reward Expansion</a>
      </td>
      <td style="text-align:left">
        <p>POSDAO open to public participation.</p>
        <ul>
          <li>20k STAKE minimum for validator candidates</li>
          <li>1K STAKE minimum for delegators</li>
        </ul>
      </td>
      <td style="text-align:left">Anticipated:
        <br />Q3-Q4 2020</td>
    </tr>
    <tr>
      <td style="text-align:left">3) <a href="./#phase-3-honeybadger-bft-consensus-layer-integration">HoneyBadger BFT Consensus Layer Integration</a>
      </td>
      <td style="text-align:left">New consensus integration - details TBD</td>
      <td style="text-align:left">TBD</td>
    </tr>
  </tbody>
</table>

## ✅ Phase 1: Preparation and Permissioned POSDAO

Phase 1 was successfully activated April 1, 2020.

POSDAO will launch on the xDai chain with the [current xDai validators](https://validators.poa.network/). **Public validators and delegators will be incorporated in phase 2.**

### Phase 1 STAKE Info

* Current validators each receive 20,000 STAKE at the start of the protocol. To participate, the entire amount must be staked.
* Initial validators will receive 15% APR in STAKE rewards \(eg 20k STAKE in protocol =~ 250 STAKE / Mo\) . This rate is subject to adjustment in phase 2.
* STAKE will be compartmentalized within the xDai chain. It cannot be moved to the Ethereum mainnet until phase 2.

### Timeline

| Task | Date |
| :--- | :--- |
| POSDAO finalization & testing | March 1 - 30 |
| Dai -&gt; Chai conversion mechanism | March 25 |
| POSDAO v1 migration & validator staking | April 1 |

### Details

In preparation for POSDAO migration, we will complete all required changes to the [Open Ethereum client](https://github.com/poanetwork/open-ethereum) and xDai bridge, and complete all necessary testing. We will provide current validators with detailed upgrade instructions and 20,000 STAKE tokens \(the minimum required amount to become a validator\). **In order to participate, validators must upgrade their nodes by March 31**. 

POSDAO v1 is scheduled to go live with current validators on April 1. Public staking will not be activated in phase 1.

POSDAO includes a multi-reward structure for stakers. In addition to STAKE rewards, stakers receive additional xDai rewards.  To create these rewards, Dai locked in the bridge contract is converted to [Chai](https://chai.money/about.html), an interest earning form of Dai. The interest accumulated from the locked Chai during a staking epoch is divided amongst stakers at the end of each epoch. In phase 1, we will enable Chai conversion on the xDai bridge. **However, xDai reward dividends will be not be incorporated until phase 2.** [More info on Chai is available here.](../stake-reward-mechanics/xdai-rewards/chai-faqs.md)

## Phase 2: Easy Staking, Public Staking & Reward Expansion

{% hint style="info" %}
In progress
{% endhint %}

After the STAKE public listing is complete and POSDAO is running as expected with the current validator set, staking on xDai will start with EasyStaking and then open up to all public STAKE holders.  Dates for the following upgrades are subject to the STAKE listing date and are currently TBD. In the interim, token holders can participate as mock delegators in the [pre-staking initiative offered by BitMax](pre-staking-program.md). 

### ✅ EasyStaking on Ethereum

EasyStaking is now live at: [https://easy-staking.xdaichain.com/](https://easy-staking.xdaichain.com/)  
EasyStaking Contract: [https://etherscan.io/address/0xecbcd6d7264e3c9eac24c7130ed3cd2b38f5a7ad](https://etherscan.io/address/0xecbcd6d7264e3c9eac24c7130ed3cd2b38f5a7ad)

The EasyStaking application will be deployed to the Ethereum Mainnet, and will allow participants with any amount of STAKE to participate. Users can commit STAKE to the protocol, and it will earn additional STAKE based on how long it is placed in the application as well as the total amount staked by all participants.  For more details, see the [EasyStaking page](../easy-staking/).

* Minimum &lt;.0001 STAKE, no Maximum
* Rewards based on time and total amount staked
* [EasyStaking parameters](../easy-staking/easy-staking-parameters.md)

### POSDAO Staking on xDai

* Validator Candidate: 20,000 STAKE Minimum
* Delegator: 1,000 STAKE Minimum
* STAKE reward % will vary based on role \(validator or delegator\) and amount of total STAKE locked in the protocol. The APR may be adjusted from phase 1 \(15%\). For more details, see the [reward distribution section of the POSDAO whitepaper](https://forum.poa.network/t/posdao-white-paper/2208).
* The STAKE bridge will open bi-directionally, allowing STAKE to flow freely from the Ethereum mainnet to the xDai chain and back. 

### Processes

| Task | Date |
| :--- | :--- |
| [Pre-staking on BitMax](https://btmx.com/#/staking/details/STAKE-S) | 05/05/2020 |
| [EasyStaking](../easy-staking/) | 05/08/2020 |
| Open bi-directional STAKE bridge | TBD |
| Enable staking for new validator candidates | TBD  |
| Enable public delegation | TBD  |
| Enable bridge exit reward \(additional STAKE reward\) | TBD |
| Enable xDai Chai-based reward | TBD  |

### Public Staking Details

Public participation will open in phase 2. Individuals can acquire STAKE on the mainnet \([how to get STAKE](../stake-token/get-stake/)\) and 

1. Immediately stake it into the EasyStaking application \(see [EasyStaking](../easy-staking/) for more info\)
2.  Bridge it to the xDai chain. Here, it can be used in the protocol to secure the chain and earn staking rewards. STAKE actions on xDai will be intuitive and easy to perform through the staking UI.

**POSDAO Staking on xDai** 

Individuals with enough STAKE \(20k minimum\) and the ability to run a node may register as validator candidates. STAKE can also be delegated on validator candidates, forming a pool. Candidate pools with the most STAKE will have the greatest chance of selection to the next validator set \(if there are more than 19 validator pools. If 19 or less all candidates become validators\). 

Validator sets will update after each staking epoch, initially set at 1 week intervals.

With public participation, additional rewards will be added to the protocol.

1. A fee will be charged when xDai is converted to Dai through the xDai bridge \(moved from the xDai chain to the Ethereum mainnet\). This fee \(% TBD\) will be distributed to validator pools active when the conversion occurs.
2. Interest earned from Chai locked in the bridge will be distributed as xDai to active validator pools. Additional Dai may be added to the bridge and converted to Chai to increase the interest reward at the team's discretion.

## Phase 3: HoneyBadger BFT Consensus Layer Integration

No timeline is set yet for HBBFT integration, we will provide further details once phase 2 is complete. [ More information on HBBFT is available here.](../../for-validators/consensus/honeybadger-bft-consensus/)

