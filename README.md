---
description: The first-ever USD stable blockchain and multi-chain staking token
---

# Welcome to xDai STAKE

## About

{% tabs %}
{% tab title="For users" %}
The **xDai Chain** is a stable payments blockchain designed for fast and inexpensive stable transactions. **xDai** is used for transactions, payments and fees, and **STAKE** is used to support Proof-of-Stake consensus.

**xDai** is the ideal cryptocurrency for everyday payments and transactions. Fees are extremely low, payments are **very fast**, and the value remains stable at ~ **$1 US Dollar per xDai**. User-friendly tools make xDai easily adoptable for crypto and non-crypto users alike! Users only need xDai to complete payments \(a single stable token for payments + fees\).

**STAKE** is a multi-chain staking token designed to secure the payment layer. Staking allows block producers \(validators and their delegators\) to provide transaction consensus and receive staking incentives for honest block production. **STAKE is not required for everyday chain transactions or users**, it is only required for consensus providers. STAKE is also not stable, it is a volatile token whose value is determined by the marketplace. 

See the [dual token model](for-stakers/stake-reward-mechanics/dual-token-model.md) for more on this innovative approach.
{% endtab %}

{% tab title="For developers" %}
The xDai chain is an EVM sidechain that uses a different consensus model \([POSDAO](for-validators/posdao-whitepaper.md)\) than Ethereum. The underlying architecture, however, mirrors Ethereum 1.0, meaning that smart contracts can be written and deployed in exactly the same way using a [different RPC endpoint](for-developers/developer-resources/#json-rpc-endpoints).

Any contract that works on the Ethereum mainnet can be easily redeployed to the xDai chain. On the xDai chain, transaction costs are minimized, and all fees and transactions are paid with a single token, xDai.
{% endtab %}

{% tab title="For validators" %}
Validators on the xDai chain provide consensus for transactions and secure the chain. The original xDai validator set is composed of [well known organizations in the Ethereum community](for-validators/about-xdai-validators/), and [new validator candidates can now onboard to POSDAO](for-stakers/staking-protocol/become-a-candidate-validator.md).

xDai runs on public POSDAO and [delegated Proof of Stake](for-stakers/staking-protocol/) , so anyone with enough STAKE and the ability to run a node can become a validator. Delegators help determine the validator set by placing stake on candidates they want to see become validators.
{% endtab %}

{% tab title="ELI5" %}
xDai is the name of a blockchain AND the stable cryptocurrency used on the chain. Each xDai token is worth ~ 1 US dollar.

The xDai blockchain is a sidechain of the Ethereum blockchain. This means it has the same properties as Ethereum, but uses a different method to make sure transactions are valid and consistent across all nodes in the distributed network \(consensus\). To do this, validators transmit and verify blocks every 5 seconds. Transactions can be completed quickly and fees for transactions can be minimized. 

xDai consensus uses public staking where community members can also be validator nodes that add transactions to the xDai chain. See below for more on STAKE, the token that is used for Proof of Stake consensus.

### xDai Native Token

xDai is a cryptocurrency created from the [MakerDAO DAI token](https://makerdao.com). Dai is a stable token on the Ethereum mainnet pegged to the US dollar. xDai can be acquired by users in a number of ways \([for example with a credit card](for-users/buying-xdai-with-fiat/ramp-network.md)\) but behind the scenes it is always created from Dai, and the value of xDai always corresponds 1:1 with Dai. 

Here's how xDai is created:

1. Dai is locked into a smart contract on Ethereum. This means it must remain in that contract and cannot be moved until the contract receives a verified signal to unlock it.
2. Using a bridge mechanism called the [TokenBridge](https://docs.tokenbridge.net), data about the locked Dai is transmitted to a smart contract on the xDai chain.
3. The contract on the xDai chain creates the exact same amount of xDai.
4. This xDai is then usable on the xDai chain. Users only need to switch the chain their wallet is pointing to, and xDai is available using the same Ethereum address.

When users want to exchange xDai for Dai, the process happens in reverse. xDai is burned \(destroyed\) in the xDai chain smart contract, and a verified signal is sent to unlock the exact same amount of Dai on the Ethereum mainnet. The unlocked Dai is then returned to the user’s address on the mainnet. 

### STAKE Token

The STAKE token is separate from xDai and is used to protect chain consensus. Validators commit a large amount of STAKE into a contract and agree that their nodes will produce blocks correctly and follow the rules.  If they are successful and follow the rules, they receive additional STAKE as rewards. If they do not follow the rules, they are banned from the protocol for 90 days and their STAKE is locked and unavailable to withdraw. 

Other community members can also delegate, or place STAKE on validators they would like to see running nodes in the network. Validators are selected each week based on how much STAKE is in their pools \(STAKE they have provided as well as STAKE delegators have provided\) as well as a random number, which makes sure the selection process is fair. 

STAKE is also used for voting purposes, where [community members can create and vote on proposals](for-stakers/stake-token/stake-weighted-voting/) about the xDai protocol \(for example changing fee amounts, delegation amounts etc.\)
{% endtab %}
{% endtabs %}

## **Reasons to Use the xDai Stable Chain:**

* ✅Fast transaction times \(5 seconds\) & low transaction fees \(500 tx for $.01\).
* ✅Digital cash. A stable chain is ideal for real world value exchange where 1 xDai = 1 US Dollar.
* ✅A single token for transactions & gas fees.
* ✅On-chain, decentralized [Random Number Generator](for-developers/on-chain-random-numbers/).
* ✅Permissionless delegated Proof-Of-Stake based consensus with public [POSDAO](for-validators/posdao-whitepaper.md).
* ✅[STAKE token](for-stakers/stake-token/) allows community consensus participation and incentives. 
* ✅Wide-ranging Community Support \(see [xDai Validator Organizations](for-validators/about-xdai-validators/current-xdai-validators/)\).
* ✅Outstanding energy efficiency.
* ✅Extreme usability with tools like [Burner Wallet](for-users/wallets/burner-wallet.md) & [Burner Wallet 2](for-users/wallets/burner-wallet-2.md).
* ✅Growing ecosystem designed to support stable person-to-person transactions, micro transactions, [conference currencies](about-xdai/use-cases/cryptocurrency-for-events-and-conferences/), [community currencies](about-xdai/use-cases/community-currencies.md) and more.
* ✅Smart Contract, DApp & toolset compatibility with other Ethereum-based chains like Ethereum, Ethereum Classic and others.
* ✅Experiencing the [magic of crypto](about-xdai/news-and-information/crypto-influencers-on-xdai.md#anthony-pompliano) for the first time!

![xDai on the BlockScout.com Blockchain Explorer](.gitbook/assets/xdai_explorer.png)

## \*\*\*\*

