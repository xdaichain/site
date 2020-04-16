---
description: The first-ever USD stable blockchain
---

# Welcome to xDai

## About

{% tabs %}
{% tab title="For users" %}
xDai is the ideal cryptocurrency for everyday payments and transactions. Fees are extremely low, payments are **instantaneous**, and the value remains stable at ~ **$1 US Dollar per xDai**. User-friendly tools make xDai easily adoptable for a broad audience \(crypto and non-crypto users alike!\)
{% endtab %}

{% tab title="For developers" %}
The xDai chain is an EVM sidechain that uses a different consensus model \([POSDAO](for-validators/posdao-whitepaper.md)\) than Ethereum. The underlying architecture, however, mirrors Ethereum 1.0, meaning that smart contracts can be written and deployed in exactly the same way using a [different RPC endpoint](for-developers/developer-resources.md#json-rpc-endpoints).

Any contract that works on the Ethereum mainnet can be easily redeployed to the xDai chain. On the xDai chain, transaction costs are minimized, and all fees and transactions are paid with a single token, xDai.
{% endtab %}

{% tab title="For validators" %}
Validators on the xDai chain provide consensus for transactions and secure the chain. Current xDai validators are [well known organizations in the Ethereum community](for-validators/about-xdai-validators.md), and are elected by other validators in an on-chain governance process.

When xDai switches to public POSDAO and delegated Proof of Stake, anyone with enough STAKE and the ability to run a node will have the opportunity to become a validator. Delegators in this model will help determine the validator set by placing stake on candidates they want to see become validators.
{% endtab %}

{% tab title="ELI5" %}
xDai is the name of a blockchain AND the stable cryptocurrency used on the chain. Each xDai token is worth ~ 1 US dollar.

The xDai blockchain is a sidechain of the Ethereum blockchain. It has the same properties as Ethereum, but uses a different consensus method to make sure transactions are valid and consistent across all nodes in the distributed network. Currently, known organizations \(called validators\) transmit and verify blocks every 5 seconds. This means transactions can be completely quickly and fees for transactions can be minimized.

xDai is a cryptocurrency created from the [MakerDAO DAI token](https://makerdao.com). Dai is a stable token on the Ethereum mainnet pegged to the US dollar. xDai can be acquired by users in a number of ways \([for example with a credit card](for-users/buying-xdai-with-carbon/)\) but behind the scenes it is always created from Dai, and the value of xDai always corresponds 1:1 with Dai. 

Here's how xDai is created:

1. Dai is locked into a smart contract on Ethereum. This means it must remain in that contract and cannot be moved until the contract receives a verified signal to unlock it.
2. Using a bridge mechanism called the [TokenBridge](https://docs.tokenbridge.net), data about the locked Dai is transmitted to a smart contract on the xDai chain.
3. The contract on the xDai chain creates the exact same amount of xDai.
4. This xDai is then usable on the xDai chain. Users only need to switch the chain their wallet is pointing to, and xDai is available using the same Ethereum address.

When users want to exchange xDai for Dai, the process happens in reverse. xDai is burned \(destroyed\) in the xDai chain smart contract, and a verified signal is sent to unlock the exact same amount of Dai on the Ethereum mainnet. The unlocked Dai is then returned to the user’s address on the mainnet.
{% endtab %}
{% endtabs %}

![xDAi on the BlockScout Blockchain Explorer](.gitbook/assets/screen-shot-2019-10-07-at-12.29.35-pm.png)

## **Reasons to Use the xDai Stable Chain:**

* ✅Fast transaction times \(5 seconds\) & low transaction fees \(500 tx for $.01\).
* ✅Digital cash. A stable chain is ideal for real world value exchange where 1 xDai = 1 US Dollar.
* ✅Single token for transactions & gas fees.
* ✅On-chain, decentralized [Random Number Generator](for-developers/on-chain-random-numbers/).
* ✅Permissionless delegated Proof-Of-Stake based consensus with public [POSDAO ](for-validators/posdao-whitepaper.md)\(coming soon - currently transitioning from private to public POSDAO\).
* ✅[STAKE token](for-stakers/stake-token/) allows community members to participate in consensus and receive incentives.
* ✅Wide-ranging Community Support \(see [xDai Validator Organizations](about-xdai/news-and-information/current-xdai-validators.md)\).
* ✅Extreme usability with tools like Burner Wallet & Burner Wallet 2.
* ✅Growing ecosystem designed to support stable person-to-person transactions, micro transactions, [conference currencies](about-xdai/use-cases/cryptocurrency-for-events-and-conferences/), [community currencies](about-xdai/use-cases/community-currencies.md) and more.
* ✅Smart Contract, DApp & toolset compatibility with other Ethereum-based chains like Ethereum, Ethereum Classic and others.
* ✅Experiencing the [magic of crypto](media/crypto-influencers-on-xdai.md#anthony-pompliano) for the first time!

