# OmniBridge \(for all other ERC20 tokens\)

{% hint style="warning" %}
**Note: Transfers are non-reversible**. If you initiate and complete the first request transaction, you will need to complete the 2nd claim transaction at some time to receive your tokens on chain. This can be very expensive on Ethereum Mainnet. You can wait for gas prices to drop and claim at a later time if you like. In addition, MetaMask cost estimates may be inaccurate.   
  
[**See this post for more information on the claims process and costs to claim**](https://forum.poa.network/t/request-and-claim-to-transfer-assets-from-xdai-chain/4495) **when transferring tokens from xDai to Ethereum using the OmniBridge.**
{% endhint %}

OmniBridge can be used to bridge any existing ERC20 on Ethereum Mainnet to xDai and back. The first time a token is bridged, a new ERC677 token contract is deployed on xDai and the token name is extended to include "on xDai". If a token has been bridged previously, the previously deployed contract is used. In both cases, the requested amount of tokens is minted and sent to the account that initiated the transfer.

{% hint style="info" %}
**OmniBridge and OmniBridge UI are Beta software, use at your own risk.**

**Bridge Interfaces**

🌉[OmniBridge UI ](https://omni.xdaichain.com/)live link  
  
🌉[Transaction Monitor](https://alm-xdai.herokuapp.com/): Use it to see updated transaction status.
{% endhint %}

{% hint style="success" %}
**Resources**

* Video Tutorial - [Move STAKE between Ethereum to xDai with the OmniBridge](https://youtu.be/qbuBqur9lcE)
* Instructions to [Bridge any ERC20 from Ethereum to xDai](https://docs.tokenbridge.net/eth-xdai-amb-bridge/multi-token-extension/ui-to-transfer-tokens/transfer-erc20)
* OMNI Bridged Token List on BlockScout: [https://blockscout.com/xdai/mainnet/bridged-tokens](https://blockscout.com/xdai/mainnet/bridged-tokens)
* HoneySwap tutorials: Basics for swapping tokens and other information related to HoneySwap exchange - [https://forum.1hive.org/t/1hive-101-beeginner-video-tutorials/217](https://forum.1hive.org/t/1hive-101-beeginner-video-tutorials/217)
{% endhint %}

### Additional Information

{% embed url="https://docs.tokenbridge.net/eth-xdai-amb-bridge/multi-token-extension" %}

{% hint style="warning" %}
Note there are 2 bridges to xDai, the xDai - Dai bridge and the Omnibridge. **If you want to bridge xDai to Dai or vice versa, use the** [**xDai Bridge.**](converting-xdai-via-bridge/)\*\*\*\*
{% endhint %}

