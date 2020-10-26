# OmniBridge \(for all other ERC20 tokens\)

OmniBridge can be used to bridge any existing ERC20 on Ethereum Mainnet to xDai and back. The first time a token is bridged, a new ERC677 token contract is deployed on xDai and the token name is extended to include "on xDai". If a token has been bridged previously, the previously deployed contract is used. In both cases, the requested amount of tokens is minted and sent to the account that initiated the transfer.

{% hint style="info" %}
**OmniBridge and OmniBridge UI are experimental software in Beta, use at your own risk.**

**Bridge Interfaces**

🌉[OmniBridge UI](https://xdai-omnibridge.web.app/) live link  
  
🌉[Transaction Monitor](https://alm-xdai.herokuapp.com/): Use it to see updated transaction status.
{% endhint %}

{% hint style="success" %}
**Resources**

* Instructions to [Bridge any ERC20 from Ethereum to xDai](https://docs.tokenbridge.net/eth-xdai-amb-bridge/multi-token-extension/ui-to-transfer-tokens/transfer-erc20)
* OMNI Bridged Token List on BlockScout: [https://blockscout.com/poa/xdai/bridged-tokens](https://blockscout.com/poa/xdai/bridged-tokens)
* HoneySwap tutorials: Basics for swapping tokens and other information related to HoneySwap exchange - [https://forum.1hive.org/t/1hive-101-beeginner-video-tutorials/217](https://forum.1hive.org/t/1hive-101-beeginner-video-tutorials/217)
{% endhint %}

### Additional Information

{% embed url="https://docs.tokenbridge.net/eth-xdai-amb-bridge/multi-token-extension" %}

{% hint style="warning" %}
Note there are 2 bridges to xDai, the xDai - Dai bridge and the Omnibridge. **If you want to bridge xDai to Dai or vice versa, use the** [**xDai Bridge.**](converting-xdai-via-bridge/)\*\*\*\*
{% endhint %}

