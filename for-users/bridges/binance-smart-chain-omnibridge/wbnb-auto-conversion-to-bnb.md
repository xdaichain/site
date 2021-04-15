---
description: >-
  Bridge WBNB from xDai to BNB on BSC to begin transacting immediately on
  Binance Smart Chain
---

# WBNB auto-conversion to BNB

The BSC Bridge now supports wrapped BNB \(WBNB\) to BNB conversions directly from xDai. 

1. Swap for WBNB on xDai
2. Bridge it to BNB on Binance Smart Chain \(BSC\)
3. Use this BNB for transactions on BSC \(including bridging additional tokens from xDai to BSC\).

## 1\) Swap for WBNB

Use a DEX to swap your token on xDai for WBNB. In this example we use [HoneySwap](https://app.honeyswap.org/#/swap) to convert xDai to WBNB.

1\) Go to [app.honeyswap.org](https://app.honeyswap.org/#/swap). Connect your MetaMask wallet to xDai and select the pairs you want to trade. In this example we will swap XDAI to WBNB, but **you can swap any token with enough liquidity to WBNB**.

![](../../../.gitbook/assets/hs1.png)

2\) WBNB may not be in the Token Dropdown. To add, copy in the WBNB address on xDai - [0xCa8d20f3e0144a72C6B5d576e9Bd3Fd8557E2B04](https://blockscout.com/xdai/mainnet/tokens/0xCa8d20f3e0144a72C6B5d576e9Bd3Fd8557E2B04/token-transfers) - and select the token.

![](../../../.gitbook/assets/hs2.png)

3\) Enter in the amount to Swap and you will see the amount you will receive in WBNB. Click the swap button to continue.

![](../../../.gitbook/assets/hs-3.png)

4\) Confirm the swap on Honeyswap and then in MetaMask.

![](../../../.gitbook/assets/hs-4.png)

## 2\) Bridge WBNB to BNB on Binance Smart Chain \(BSC\)

Once your swap is complete, you will move WBNB across the bridge to receive BNB on BSC.

1\) Go to the Omni Bridge [https://omni.xdaichain.com/bridge](https://omni.xdaichain.com/bridge)

1. Select **BSC &lt;-&gt; xDai** from the Dropdown. Your MetaMask should still be connected to the xDai Chain.
2. Choose **Wrapped BNB on xDai** and **enter the amount** you want to bridge.
3. **Toggle to Receive BNB**. When your transaction is bridged, the WBNB is also unwrapped on the Binance Smart Chain as a part of the transaction! This gives you native BNB on BSC.
4. Click **Request** to begin bridging.

![](../../../.gitbook/assets/b1.png)

2\) Click to **Continue** and **confirm** the transaction in MetaMask.

![](../../../.gitbook/assets/b2-a.png)

![](../../../.gitbook/assets/b2-b.png)

3\) While transaction is processing, you can view progress in the ALM Monitor _\(optional\)_

![](../../../.gitbook/assets/alm-1.png)

![](../../../.gitbook/assets/alm-2.png)

4\) Once complete, switch to the Binance Smart Chain in MetaMask in order to claim.

{% hint style="info" %}
 If you have not added BSC to MetaMask yet, you can[ easily add here](https://chainlist.org/) or use the following params for MM custom network \(Network Name: BSC Mainnet New RPC URL: [https://bsc-dataseed.binance.org/](https://bsc-dataseed.binance.org/) ChainID: 56 Symbol: BNB Block Explorer URL: [https://bscscan.com/](https://bscscan.com/) \)
{% endhint %}

![](../../../.gitbook/assets/bs-1.png)

![](../../../.gitbook/assets/bs-2.png)

5\) Claim your tokens and confirm in MetaMask. 

{% hint style="warning" %}
Note: you may see an Insufficient Funds warning in MetaMask for a few moments while unwrap is processed, added to your account and reflected on MM. This should resolve fairly quickly and you can proceed.
{% endhint %}

![](../../../.gitbook/assets/claim-1.png)

![](../../../.gitbook/assets/claim-2.png)

6\) Once the claim is processed, you will have native BNB in your wallet on the Binance Smart Chain. You can use this for transactions as needed, and to pay tx costs for bridging over other tokens from xDai. 

![](../../../.gitbook/assets/bnb-1.png)

{% hint style="info" %}
You can also bridge in the opposite direction, moving native BNB on Binance Smart Chain to wrapped BNB on xDai. In this case, BNB is the first token in the list if BSC is the active network in MetaMask.
{% endhint %}

![](../../../.gitbook/assets/image-13-%20%281%29.png)

#### 



