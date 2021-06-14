---
description: >-
  xDai tokens are transactional tokens on the xDai chain and also used to pay
  for execution of smart contracts and gas fees.
---

# xDai Token

xDai tokens are used to pay for gas and transactions on the xDai chain. They are a stable token \(worth ~ 1 USD\) created from locked Dai. _Note that xDai features a dual token model with xDai as the stable transaction currency and STAKE as the staking/utility token._ [_Info on STAKE_](../../for-stakers/stake-token/)_._

### **How to get xDai stable tokens**

* From another user on the xDai Chain.
* Converting Dai to xDai using the [xDai Bridge](../bridges/converting-xdai-via-bridge/).
* Purchase directly on [AscendEx \(formerly Bitmax\) with the xDai/USDT Pair](https://bitmax.io/en/basic/cashtrade-spottrading/usdt/xdai).
* Purchase directly with fiat using [Ramp.Network](https://ramp.network/buy/?swapAsset=XDAI) or [MtPelerin](https://www.mtpelerin.com/buy-xdai#).
* Trading on [Honeyswap](https://honeyswap.org/) \(you will need a small amount of xDai to start trading\).
* Small amounts to pay for transactions can be acquired from the [xDai faucet](xdai-faucet.md) or by asking [Discord Community Members](https://discord.gg/mPJ9zkq).

### xDai Native Token

xDai is a cryptocurrency created from the [MakerDAO DAI token](https://makerdao.com/). Dai is a stable token on the Ethereum mainnet pegged to the US dollar. xDai can be acquired by users in a number of ways \([for example with a credit card](buying-xdai-with-fiat/ramp-network.md)\) but behind the scenes it is always created from Dai, and the value of xDai corresponds 1:1 with Dai. Here's how xDai is created:

1. Dai is locked into a smart contract on Ethereum. This means it must remain in that contract and cannot be moved until the contract receives a verified signal to unlock it.
2. Using a bridge mechanism called the [TokenBridge](https://docs.tokenbridge.net/), data about the locked Dai is transmitted to a smart contract on the xDai chain.
3. The contract on the xDai chain creates \(mints\) the exact same amount of xDai.
4. This xDai is then usable on the xDai chain. Users only need to [switch the network in their wallet](../wallets/metamask/metamask-setup.md#setting-up-metamask-for-xdai), and xDai is available using the same Ethereum address.

When users want to exchange xDai for Dai, the process is executed in reverse. xDai is burned \(destroyed\) in the xDai chain smart contract, and a verified signal is sent to unlock the exact same amount of Dai on the Ethereum mainnet. The unlocked Dai is then returned to the user’s address on the Ethereum mainnet.

{% hint style="warning" %}
**STAKE Governance Token Info:**

In addition to the xDai stable token, the ecosystem also supports STAKE, a staking and utility/governance token. STAKE price is volatile and can be traded on CEXs and DEXs both on Ethereum and the xDai Chain.  
  
_-&gt;_ [_Learn more about STAKE and how to get STAKE_](../../for-stakers/stake-token/get-stake/)_._
{% endhint %}

