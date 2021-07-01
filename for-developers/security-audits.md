---
description: Audits of xDai and related infrastructure
---

# Security Audits

## POSDAO Audit by ChainSecurity <a id="omnibridge-audit-by-chainsecurity"></a>

**Completed:** June 25, 2021

**Conclusion**: The assessment uncovered several issues which were addressed or acknowledged by the team. No "critical" severity security flaws preventing continued usage or launch of contracts in future contexts were found. 0 Critical Issues, 1 High Risk Issue Accepted, 4 Medium Issues Accepted/Acknowledged, 4 Low Risk Issues Accepted/Acknowledged.

* **Contracts:** [https://github.com/poanetwork/posdao-contracts](https://github.com/poanetwork/posdao-contracts)
* **Audit Report in repo**: [https://github.com/poanetwork/posdao-contracts/blob/master/audit/ChainSecurity/report.pdf](https://github.com/poanetwork/posdao-contracts/blob/master/audit/ChainSecurity/report.pdf)

{% embed url="https://chainsecurity.com/security-audit/poa-network-posdao/" %}

## OmniBridge Audit by ChainSecurity <a id="omnibridge-audit-by-chainsecurity"></a>

**Completed:** April 27, 2021

**Conclusion**: 0 Critical or High Risk Issues, 2 Medium Issues Accepted, 3 Low Risk Issues Accepted/Acknowledged

**Contracts:** [https://github.com/poanetwork/omnibridge](https://github.com/poanetwork/omnibridge)​

{% embed url="https://chainsecurity.com/security-audit/poa-network-omnibridge/" caption="ChainSecurity Audit Report" %}

## TokenBridge Audit by Quantstamp \(covers OmniBridge\)

**Completed:** November 6, 2020

**Conclusion**: No high and medium risk issues found, all low risk issues addressed.

**Contracts:** Revised in version 5.5.0-rc0 to address audit. [https://github.com/poanetwork/tokenbridge-contracts/releases/tag/5.5.0-rc0](https://github.com/poanetwork/tokenbridge-contracts/releases/tag/5.5.0-rc0)

{% hint style="success" %}
[Quantstamp Security Audit PDF](https://github.com/poanetwork/tokenbridge/blob/master/audit/quantstamp/POA-Network-TokenBridge-contracts-5.4.1-security-assessment-report.pdf)
{% endhint %}

## EasyStaking Audit by Quantstamp

**Completed:** August 3, 2020

**Conclusion:** All high/medium/low risk issues resolved.

{% file src="../.gitbook/assets/xdai-easy-staking-final-report.pdf" caption="Easy Staking Final Audit Report by Quantstamp" %}

## TokenBridge Audit by Quantstamp \(covers xDai bridge functionality\)

**Completed:** January 8, 2020

**Conclusion**: All high risk issues resolved and low risk issues addressed. [More information available in this post](%20https://forum.poa.network/t/quantstamp-security-audit-for-tokenbridge-contracts-completed/3233).

**Contracts:** Revised in version 3.3.0 to address audit. [https://github.com/poanetwork/tokenbridge-contracts/releases/tag/3.3.0](https://github.com/poanetwork/tokenbridge-contracts/releases/tag/3.3.0)

{% hint style="success" %}
[Quantstamp TokenBridge Security Audit PDF](https://github.com/poanetwork/tokenbridge/blob/73d500210546e2959536dc569f1aec5752077225/audit/quantstamp/POA-Network-Token-bridge-security-assessment-report.pdf)
{% endhint %}

## STAKE Token Distribution by Quantstamp

#### **STAKE Token Distribution Audit**

**Completed:** June 24, 2020  
  
**Conclusion**: No High or Medium risks, all low and informational risks addressed

{% hint style="success" %}
[Quantstamp STAKE Security Audit PDF](https://github.com/xdaichain/stake-token/blob/master/audit/Quantstamp/xDAI%20STAKE%20Token%20Distribution%20-%20Additional%20Report.pdf)
{% endhint %}

#### **DPOS Audit**

In the original audit,  the working name for the staking token was DPOS. This changed to STAKE.

**DPOS Audit Completed:** September 5, 2019  
  
**Conclusion**: All risks resolved.   
  
**Contracts:** Version 1.0.1 addressed items in audit.  
[https://github.com/xdaichain/stake-token/releases/tag/v1.0.1](https://github.com/xdaichain/stake-token/releases/tag/v1.0.1)

{% hint style="success" %}
[Quantstamp DPOS Security Audit PDF](https://github.com/xdaichain/stake-token/blob/master/audit/Quantstamp/DPOS%20token-Audit%20Final%20Report.pdf)
{% endhint %}

#### **STAKE Legal Opinion**

The token constitutes a VFA in terms of Maltese law. Please contact [team@xdaichain.com ](mailto:team@xdaichain.com)to request access to the document.

## POSDAO Initial Security Audit by PepperSec

**Completed**: August 2019

**Conclusion**: All issues fixed or addressed. Due to scalability concerns, teams created a new methodology to accumulate and later “pull” their stakes and rewards instead of the “push” strategy as implemented in the audited version of the contracts.

**Contracts:** Version 0.1.0 addresses issues present in audit. [https://github.com/poanetwork/posdao-contracts/releases/tag/v0.1.0](https://github.com/poanetwork/posdao-contracts/releases/tag/v0.1.0)

{% hint style="success" %}
[POSDAO v1 Consensus Contracts audit](https://forum.poa.network/t/security-audits-of-posdao-consensus-contracts/2921)
{% endhint %}

