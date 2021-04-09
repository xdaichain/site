# xDai Chain Basics

## Who is xDai?

* The [xDai development team](https://www.xdaichain.com/media/xdai-dev-team) is made up of an experienced group of long-time blockchain & sidechain developers. 
* Collaborators include [initial validators ](../../for-validators/about-xdai-validators/original-xdai-validators/)like MakerDAO, Gnosis, and SyncNode & [projects that support the ecosystem](../../for-developers/developer-resources/#dapp-management-and-developer-tools) like theGraph, Tenderly and AnyBlock Analytics. 
* Users are worldwide, from crypto veterans to first-time users.

## What is xDai?

* xDai is the name of the stablechain **and** the stable native coin that lives on the chain. 
* The xDai chain is an Ethereum-based stable sidechain implementing a dPOS consensus called POSDAO. 
* The xDai coin is used for stable transactions and low, stable fees. It can also be used to back on-chain tokens \(use cases for this include [Event Currencies](../use-cases/cryptocurrency-for-events-and-conferences/) and [Community Currencies](../use-cases/community-currencies.md)\)

## When is xDai?

* The xDai Stable Chain has been live since October, 2018. 
* POSDAO \(Proof-of-Stake\) consensus for selected validators was implemented April 1, 2020. 
* Decentralized public staking with the STAKE token is coming Q1 2021.
* More on [xDai'sPast](https://forum.poa.network/t/xdai-the-birth-of-the-stable-chain/2812)
* More on [xDai's Future](../roadmap/)

## Where is xDai?

xDai is a stablechain located within the vast Ethereum ecosystem. xDai users are located around the world, from small gatherings, to 1000+ participant conferences, to networks of villages in Kenya.

**Connecting to xDai:**

* Network ID: 100 
* Primary RPC:  [https://xdai.poanetwork.dev/](https://xdai.poanetwork.dev/)
* Explorer: [https://blockscout.com/xdai/mainnet](https://blockscout.com/xdai/mainnet)
* xDai Bridge: [https://bridge.xdaichain.com/](https://bridge.xdaichain.com/)

## Why xDai?

xDai exists to support stable payments and digital cash transactions. Whereas Ethereum transaction costs are unpredictable, subject to congestion, and require several tokens \(for example DAI + Eth for gas\), xDAi transactions are fast, very inexpensive, and require a single token \(xDai\).

xDai also supports a decentralized, earth-friendly architecture with POSDAO consensus and the STAKE consensus staking token.

➡ [xDai General Overview](../news-and-information/media-articles/xdai-chain-basic-overview-presentation.md)

## **What are xDai’s future plans?**

Plans are multi-faceted and both short and long term. In the short term, we are focused on building out the public staking interface for POSDAO. This will enable anyone to participate in staking on the xDai chain.

Long-term plans are related to features and updates to our infrastructural assets like TokenBridge & BlockScout, as well as establishing a fund for DApp development and eventual implementation of [HoneyBadger BFT](../../for-validators/consensus/honeybadger-bft-consensus/) into the protocol.

**Roadmaps:**

* Staking: [https://www.xdaichain.com/for-stakers/stake-and-staking](https://www.xdaichain.com/for-stakers/stake-and-staking) 
* xDai General: [https://www.xdaichain.com/about-xdai/roadmap](https://www.xdaichain.com/about-xdai/roadmap)  
* TokenBridge:  [https://docs.tokenbridge.net/about-tokenbridge/roadmap](https://docs.tokenbridge.net/about-tokenbridge/roadmap) 
* BlockScout: [https://docs.blockscout.com/about/roadmap](https://docs.blockscout.com/about/roadmap)

## How does the xDai chain address scalability concerns? 5 second blocks are fast, but many chains offer even faster transactions.

We are looking at both vertical and horizontal scalability opportunities to ensure xDai can scale as required. With vertical scalability xDai's validators optimize their nodes and apply protocol upgrades to push the limits of technologies. With horizontal scalability additional chains can be launched in the same manner and connected by the TokenBridge protocol. It's our vision of sharding in a realm based manner.

## What is the TPS \(transactions per second or tx/sec\) for the xDai Chain?

It depends on the type of transaction being sent, for the simplest transactions the xDai chain can process 70 tx/sec.

## Is the xDai chain secure?

We have contracted 3rd party security firms to conduct [comprehensive audits ](../../for-developers/security-audits.md)on the xDai consensus, tokens, bridge and underlying architecture. We have resolved any issues they have found, and are committed to ongoing audits and comprehensive testing. However, we cannot anticipate all issues and users must assume risk when using any blockchain technologies.

## I accidentally transferred funds to a contract address - what should I do?

It depends on the nature of the contract. If you accidentally sent to a token contract on xDai \(for example the [STAKE,](https://blockscout.com/xdai/mainnet/tokens/0xb7D311E2Eb55F2f68a9440da38e7989210b9A05e/token-transfers) [LINK ](https://blockscout.com/xdai/mainnet/tokens/0xE2e73A1c69ecF83F464EFCE6A5be353a37cA09b2/token-transfers)or other bridged tokens\), it may be possible for validators to retrieve these funds using the `claimTokens` functionality. However, this requires additional coordination and signature collection. **If we are able to claim, there is a 10% fee to claim your mis-sent tokens**.

This fee is then used to benefit the protocol. The team uses it to trade for STAKE tokens on Uniswap and then burn these STAKE tokens. In the future, MetaMask is planning to implement a warning message to help prevent sending funds to a token contract on accident. 

If you accidentally sent to a contract, you can reach out to the [team on Discord](https://discord.gg/mPJ9zkq) to see if they can help you.

