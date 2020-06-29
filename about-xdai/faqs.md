---
description: Basic Project FAQs
---

# FAQs

{% hint style="info" %}
FAQs are in progress, we are continuing to add to this document. If you have a question that is not answered here, please ask in our [Telegram](https://t.me/xdaistable) or [Forum](use-cases/stable-platform-for-smart-contracts.md).
{% endhint %}

## How do I find the information I need?

There is a lot to know about xDai, so we've split the website into several sections, depending on your role and what you info you might need to access.

* **About xDai**: General features, overview, latest news and information designed for new users or those who want to learn more about xDai.
* **For Users**: If you want to transact with xDai, use xDai DApps or wallets.
* **For Stakers**: If you want to delegate STAKE on chain and earn rewards, or become a validator candidate. This section is related to xDai consensus and the STAKE token, which protects the chain.
* **For Developers**: If you want to build on xDai, all the resources you need are in this section.
* **For Validators**: This section is geared towards validators - setting up and running a node, bridge validator info, and other information. This section will change as the chain transforms to public validation.
* **Contact & Media**: To reach us, or gather assets for interviews.

## xDAI  Basics: The 5Ws \(Who, What, When, Where, Why\)   

### Who is xDai?

* The [xDai development team](https://www.xdaichain.com/media/xdai-dev-team) is made up of an experienced group of long-time blockchain & sidechain developers. 
* Collaborators include [initial validators ](news-and-information/current-xdai-validators.md)like MakerDAO, Gnosis, and SyncNode & [projects that support the ecosystem](../for-developers/developer-resources/#dapp-management-and-developer-tools) like theGraph, Tenderly and AnyBlock Analytics. 
* Users are worldwide, from crypto veterans to first-time users.

### What is xDai? 

* xDai is the name of the stablechain **and** the stable native coin that lives on the chain. 
* The xDai chain is an Ethereum-based stable sidechain implementing a dPOS consensus called POSDAO. 
* The xDai coin is used for stable transactions and low, stable fees. It can also be used to back on-chain tokens \(use cases for this include [Event Currencies](use-cases/cryptocurrency-for-events-and-conferences/) and [Community Currencies](use-cases/community-currencies.md)\)

### When is xDai?

* The xDai Stable Chain has been live since October, 2018. 
* POSDAO \(Proof-of-Stake\) consensus for selected validators was implemented April 1, 2020. 
* Decentralized public staking with the STAKE token is coming Q3 2020.
* More on [xDai'sPast](https://forum.poa.network/t/xdai-the-birth-of-the-stable-chain/2812)
* More on [xDai's Future](roadmap.md)

### Where is xDai?

xDai is a stablechain located within the vast Ethereum ecosystem. xDai users are located around the world, from small gatherings, to 1000+ participant conferences, to networks of villages in Kenya. 

**Connecting to xDai:**

* Network ID: 100 
* Primary RPC:  [https://xdai.poanetwork.dev/](https://xdai.poanetwork.dev/)
* Explorer: [https://blockscout.com/poa/xdai](https://blockscout.com/poa/xdai)
* Burner Wallet: [https://xdai.io](https://xdai.io)

### Why xDai?

xDai exists to support stable payments and digital cash transactions. Whereas Ethereum transaction costs are unpredictable, subject to congestion, and require several tokens \(for example DAI + Eth for gas\), xDAi transactions are fast, very inexpensive, and require a single token \(xDai\).

xDai also supports a decentralized, earth-friendly architecture with POSDAO consensus and the STAKE consensus staking token.

➡ [xDai General Overview](news-and-information/media-articles/xdai-chain-basic-overview-presentation.md)

## xDai Ecosystem: Tools, Wallets, DApps

### How can I find statistics on xDai transactions, user addresses etc?

BlockScout is a full-featured, open-source explorer that supports xDai. It lets you explore all transactional aspects on chain.

* BlockScout access: [https://blockscout.com/poa/xdai](https://blockscout.com/poa/xdai)
* BlockScout docs: [https://docs.blockscout.com/](https://docs.blockscout.com/)

### **What wallets are available to use with xDai?**

We are fortunate to have the support of quite a number of wallets, including some amazing mobile wallets like AlphaWallet, DEX wallet ****and Poketto, and web wallets like Portis Wallet. You can use MetaMask, and Nifty Wallet and Saturn Wallet are additional web3 wallets similar to MetaMask but containing additional features that natively support xDai.  
  
The biggest wallet use case is Burner Wallet - as this is really designed for small, stable payments and for conferences and events. We invite you to [check out our wallets page](../for-users/wallets/) for more information.

### How can I develop and deploy a DApp on xDai?

Since xDai is an Ethereum-compatible sidechain, you can use the same tools \(like Truffle\), languages \(Solidity\) and environments you are used to using with Ethereum. With a few quick tweaks, your DApp can also be running on xDai. See [Smart Contract Deployment](../for-developers/smart-contract-deployment.md) for details.

### **What are xDai’s future plans?**

Plans are multi-faceted and both short and long term. In the short term, we are focused on building out the public staking interface for POSDAO. This will enable anyone to participate in staking on the xDai chain.

Long-term plans are related to features and updates to our infrastructural assets like TokenBridge & BlockScout, as well as establishing a fund for DApp development and eventual implementation of [HoneyBadger BFT](../for-validators/consensus/honeybadger-bft-consensus/) into the protocol.

**Roadmaps:** 

* Staking: [https://www.xdaichain.com/for-stakers/stake-and-staking](https://www.xdaichain.com/for-stakers/stake-and-staking) 
* xDai General: [https://www.xdaichain.com/about-xdai/roadmap](https://www.xdaichain.com/about-xdai/roadmap)  
* TokenBridge:  [https://docs.tokenbridge.net/about-tokenbridge/roadmap](https://docs.tokenbridge.net/about-tokenbridge/roadmap) 
* BlockScout: [https://docs.blockscout.com/about/roadmap](https://docs.blockscout.com/about/roadmap)

### How does the xDai chain address scalability concerns? 5 second blocks are fast, but many chains offer even faster transactions.

We are looking at both vertical and horizontal scalability opportunities to ensure xDai can scale as required. With vertical scalability xDai's validators optimize their nodes and apply protocol upgrades to push the limits of technologies. With horizontal scalability additional chains can be launched in the same manner and connected by the TokenBridge protocol. It's our vision of sharding in a realm based manner.

### What is the TPS \(transactions per second or tx/sec\) for the xDai Chain?

It depends on the type of transaction being sent, for the simplest transactions the xDai chain can process 60 tx/sec. 

### Why is the xDai bridge / TokenBridge important?

The bridge is a key element of xDai which allows for interop between xDai and the mainnet. The TokenBridge development team just received [Ethereum Ecosystem support program funding](https://blog.ethereum.org/2020/05/07/ecosystem-support-program-allocation-update-q1/) to continue with TokenBridge development within the entire ecosystem \(not related directly to xDai but the improvements we make will also benefit the xDai chain\)

The bridge connects the networks and allows tokens to exist on both sides. If you want some xDai for transactions, you lock Dai in the bridge contract and then mint xDai on the xDai chain. You can use this xDai as digital cash for transactions, and when you are finished, you can burn the remaining xDai and unlock the corresponding amount of Dai. There’s an easy UI for it, and it works quite well to maintain liquidity.

Another extension of the same bridge infrastructure will be used to move STAKE between the mainnet and xDai.

### Is the xDai chain secure?

We have contracted 3rd party security firms to conduct [comprehensive audits ](../for-developers/security-audits.md)on the xDai consensus, tokens, bridge and underlying architecture. We have resolved any issues they have found, and are committed to ongoing audits and comprehensive testing. However, we cannot anticipate all issues and users must assume risk when using any blockchain technologies.

### Are xDai or STAKE tokens considered securities?

Based on our research and [legal opinions](../for-developers/security-audits.md#dpos-stake-token-by-quantstamp) they are not considered securities. However, the regulatory landscape may differ between countries. Please be informed of your local laws when using.

## **xDai Native Coin/Token**

### What is the main function of the xDai coin?

xDai is a stable token, used for transactions. It is bridged from Dai to the xDai chain, and used on the xDai chain for payments and gas fees. 1 xDai =  1 Dai \(and 1 Dai = approximately 1 USD\) 

### How are xDai coins minted?

xDai is created from the stable Dai token - Dai is locked in a bridge contract and the same amount of xDai is minted on the xDai chain. xDai can then be transformed back into Dai using the same bridging mechanism \(xDai is burned and Dai is minted on the Ethereum Mainnet\).

### How can I get xDai coins?

* From another user on the xDai Chain \(Wallet transfer, airdrop, payment\)
* Converting Dai to xDai using the[ xDai Bridge](https://www.xdaichain.com/for-users/converting-xdai-via-bridge)
* Buying xDai directly using Carbon \(coming soon\)

### What makes the xDai coin a different kind of stablecoin?

Imagine every time you needed to pay for lunch you had to use 2 different currencies. On top of that, one of those currencies was not stable, so you didn’t know if you would have to pay an extra $.05 or an extra $.50 in fees for the same $10.00 lunch.🍔 

This is what happens every time you use a stablecoin on the Ethereum mainnet. xDai eliminates this issue - transaction fees are stable and very low \(500 or so for $.01\). Because they are known & low costs, this also enables stable micro-transactions, which is important for contracts and projects who need to plan for application costs. 

The xDai stablechain enables digital cash, supporting small denomination transactions for everyday, stable purchases. 

### How can you mitigate stablecoin-based risks \(like broken stability pegs\) with xDai? 

The xDai bridge is expandable to include additional forms of collateral on the Ethereum side of the bridge.  Currently Dai and Chai are both supported \(SAI was also supported prior to the shutdown\). More may be added in the future. Additional types of collateral can act to mitigate stability risks.

## STAKE Staking Token

### If you only need xDai coins for transactions, what is STAKE used for?

STAKE is a volatile token used as a staking token to protect the xDai chain. It enables delegated staking and community participation in xDai consensus. 

You do not need STAKE to use the xDai chain for regular transactions. You only need STAKE if you want to be a validator or delegator on the xDai chain.

More on the [Dual Token Model](news-and-information/dual-token-model.md)

### How do I get STAKE?

* From another user on the Ethereum Mainnet \(Wallet transfer, airdrop, payment\)
* From an exchange. Currently STAKE is offered at BitMax [https://bitmax.io/\#/trade/usdt/stake](https://bitmax.io/#/trade/usdt/stake)
* From UniSwap:  [https://uniswap.exchange/swap/0x0ae055097c6d159879521c384f1d2123d1f195e6](https://uniswap.exchange/swap/0x0ae055097c6d159879521c384f1d2123d1f195e6)

### What is the STAKE contract address?

The Ethereum Mainnet contract address for STAKE is: [0x0Ae055097C6d159879521C384F1D2123D1f195e6](https://etherscan.io/token/0x0Ae055097C6d159879521C384F1D2123D1f195e6)

### I've got STAKE but can't find it in my wallet. 

You may need to add a custom token - [Instructions for doing this with MetaMask](../for-stakers/stake-token/get-stake/add-stake-to-metamask.md).

### I want to stake STAKE Now! Is it possible?

Check out the Pre-Staking program, where you can join the incentivized testnet through StakeVault and start earning rewards now!

### When does public staking start on xDai?

Public staking is scheduled to start in Q3 2020. 

### How much STAKE will I need for public staking?

Minimum amounts needed to validate or delegate on the xDai chain.

* **Validators:** 20K STAKE
* **Delegators:** 1K STAKE

### What is the STAKE Marketcap?

You can find information on the STAKE Marketcap and supply here: [https://www.coingecko.com/en/coins/xdai-stake](https://www.coingecko.com/en/coins/xdai-stake)

### How do I transfer STAKE from the Ethereum Mainnet to the xDai chain?

When public staking on xDai begins, you will need to move your STAKE to xDai in order to use it there. We will provide detailed instructions as public staking approaches.

### Why is STAKE an ERC677?

ERC677 is very similar to an ERC20, but includes additional functionality. We use the transferandCall functionality to enable easier bridge conversions, moving STAKE from the Ethereum Mainnet to the xDai chain and back. 

For more information see the EIP677 standard [https://github.com/ethereum/EIPs/issues/677](https://github.com/ethereum/EIPs/issues/677). 

### What is multi-chain staking?

xDai is the first developed use-case for STAKE. However, it may be adopted by other chains in the future and used as a staking token for their consensus as well. POSDAO consensus is an algorithm we’ve developed that may be adopted by other chains, and those chains would have the opportunity to also incorporate a ready-made solution with STAKE to protect their chain.  
****

## **Public Staking \(Validators & Delegators\)**

### What is a validator?

A validator runs a node that verifies transactions and finalizes blocks on the xDai chain. Each validator must provide the minimum STAKE collateral \(20K STAKE\) into their pool and setup a functional node to participate. They start as candidates, and have the chance to become validators each week when a new validator set is chosen.

### What is the maximum number of validators?

The max number of validators in a validator set is 19. This is called a validator set and is chosen each week from the group of validator candidates. 

### What is the maximum number of validator candidates?

The maximum number of candidates is 3000.

### How are validators selected?

If there are more than 19 suitable candidates, the top 19 are chosen based on the total amount of stake in their pool + a random number.

### What is a delegator?

A delegator is a STAKE holder who places STAKE in a validator candidates pool. If that candidate becomes a validator, the delegator also receives rewards. By placing STAKE, delegators vote on the candidates they think will make the best validators. 1K minimum delegation per validator candidate.

### How long is a staking epoch?

A staking epoch is 1 week. 

### How does a participant \(validator, candidate or delegator\) add/withdraw/claim STAKE?

A UI is in process that will allow delegators and validators to easily manage their STAKE tokens. For more info, see the [Staking Operations](../for-stakers/staking-protocol/staking-operations/) section.

### How do I get STAKE rewards as a validator/delegator?

Rewards are automatically distributed at the end of a staking epoch to active validators and delegators.

### What rewards can I expect as a participant?

See the [rewards in a dual token environment post](../for-stakers/stake-reward-mechanics/rewards-in-a-dual-token-environment.md) for more information. As a validator, you will always receive at least 30% of your pool's rewards, and more if delegators contribute less than 70% to the pool. Rewards are based on how much STAKE is staked in the protocol as well as chain-based activity \(stable rewards come from bridge fees and transactions, as well as Chai based rewards from DAI locked in the bridge\). Staking rewards will accumulate at 15% APR based on the locked amount.





