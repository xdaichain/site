# Binance Smart Chain Omnibridge

The Binance Smart Chain \(BSC\) Omnibridge allows users to move ERC20 tokens between xDai and BSC. It is provided as an additional interoperability option for users looking to access cross-chain resources and take advantage of lower fees. The [Ethereum Omnibridge](../omnibridge.md) is always available for users bridging to and from Ethereum Mainnet.

{% hint style="info" %}
**BSC OmniBridge and OmniBridge UI are beta software, use at your own risk.**

**You will need xDai and BNB on the Binance Smart Chain to complete a bridge transfer.**

**Bridge Interfaces**

🌉BSC [OmniBridge UI ](https://bsc-to-xdai-omnibridge.web.app/)live link  
  
🌉BSC [Transaction Monitor](https://alm-bsc-xdai.herokuapp.com/): Use it to see updated transaction status.

🌉[BSC tokens list](https://blockscout.com/poa/xdai/bridged-tokens/bsc)
{% endhint %}

{% hint style="warning" %}
Tokens bridged cross-chain are appended with the "on xDai" or "on BSC". There are instances where bridging across multiple chains creates token names such as "[STAKE on xDai on BSC](https://www.bscscan.com/token/0x24e5cf4a0577563d4e7761d14d53c8d0b504e337)".   

Double bridging also can result in multiple instances of the same token on a single chain. For example, USDT can be bridged to xDai from Ethereum and also bridged to xDai from BSC. This will result in 2 separate USDT token instances on xDai. These tokens cannot be merged into a single instance after they are minted. We are working on steps to address this issue in a decentralized manner without requiring prior approval to bridge. **Look for more details soon**.
{% endhint %}

### Additional Information

{% embed url="https://docs.tokenbridge.net/bsc-xdai-amb/omnibridge-extension" %}





