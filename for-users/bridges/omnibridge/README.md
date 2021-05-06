---
description: Cross Chain Bridge for Ethereum <-> xDai and BSC <-> xDai
---

# OmniBridge: ERC20 Token Transfers

## Basics

* Bridge any existing ERC20 between Ethereum and xDai & BSC and xDai.
* The first time a token is bridged, a new ERC677 token contract is deployed on xDai and the token name is extended to include "on xDai". 
* If a token has been bridged previously, the previously deployed contract is used. 
* In either case, the requested amount of tokens is minted and sent to the account that initiated the transfer.

{% hint style="success" %}
🌉 OmniBridge is available at [https://omni.xdaichain.com](https://omni.xdaichain.com/bridge)  
  
Connect your wallet to the network you want to bridge from and set the chain to either Eth &lt;-&gt; xDai or BSC &lt;-&gt; xDai  from the dropdown menu. [Bridge Tutorial](https://honeyswap.org/xdai-bridges)  
  
Monitor the status of OmniBridge Transactions with the [ALM Monitor](https://alm-xdai.herokuapp.com/)
{% endhint %}

![OmniBridge UI](../../../.gitbook/assets/omni1%20%282%29.png)

## **Features**

* [Alternate Receiver](../converting-xdai-via-bridge/alternate-receiver-send-dai-to-another-xdai-address.md): Bridge tokens from an address on one chain to a second address on another chain\).
* [Define Custom RPCs:](set-custom-rpc-endpoints.md) Set your own RPC endpoints for bridge interaction.
* Infinite Unlock: Approve all transfers of a token with a single tx rather than for each transfer.
* Reverse Mode: _Coming Soon_. Bridge tokens minted on xDai to Ethereum/BSC

## Resources

* Video Tutorial - [Move STAKE between Ethereum to xDai with the OmniBridge](https://youtu.be/qbuBqur9lcE)
* Instructions to [Bridge any ERC20 from Ethereum to xDai](https://docs.tokenbridge.net/eth-xdai-amb-bridge/multi-token-extension/ui-to-transfer-tokens/transfer-erc20)
* OMNI Bridged Token List on BlockScout: [https://blockscout.com/xdai/mainnet/bridged-tokens](https://blockscout.com/xdai/mainnet/bridged-tokens)
* OmniBridge Documentation Site: [https://docs.tokenbridge.net/eth-xdai-amb-bridge/multi-token-extension](https://docs.tokenbridge.net/eth-xdai-amb-bridge/multi-token-extension)
* 3rd party explainers
  * HoneySwap tutorials: Basics for swapping tokens and other information related to HoneySwap exchange -  [https://honeyswap.org/xdai-bridges](https://honeyswap.org/xdai-bridges) [https://forum.1hive.org/t/1hive-101-beeginner-video-tutorials/217](https://forum.1hive.org/t/1hive-101-beeginner-video-tutorials/217)
  * Cross-Bridge Explainer by Yostari - [https://yostari.medium.com/traversing-the-eth-polygon-xdai-bsc-cross-chain-bridges-cfe3b29d49d4](https://yostari.medium.com/traversing-the-eth-polygon-xdai-bsc-cross-chain-bridges-cfe3b29d49d4)

{% hint style="warning" %}
**Transfers are non-reversible**. If you initiate and complete the first request transaction, you will need to complete the 2nd claim transaction at some time to receive your tokens on chain. This can be very expensive on Ethereum Mainnet. You can wait for gas prices to drop and claim at a later time if you like. In addition, MetaMask cost estimates may be inaccurate.

[**See this post for more information on the claims process and costs to claim**](https://forum.poa.network/t/request-and-claim-to-transfer-assets-from-xdai-chain/4495) **when transferring tokens from xDai to Ethereum using the OmniBridge.**
{% endhint %}

{% hint style="warning" %}
Note there are multiple bridges to xDai, the OmniBridge is used for ERC20 cross-chain transfers. It is not used to mint Native xDai - to bridge Dai to xDai or xDai to Dai.  
  
**If you want to bridge xDai to Dai or vice versa, use the** [**xDai Bridge.**](../converting-xdai-via-bridge/)\*\*\*\*
{% endhint %}

