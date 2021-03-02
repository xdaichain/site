---
description: A tool to revoke or adjust contract allowances
---

# Revoke

Many DeFi apps require users to allow a contract to spend funds before transfers can be executed. This is necessary functionality, but can result in an unlimited allowance, which carries security risks if a contract is ever compromised, has an unknown bug, or if there are other issues. Examples of applications on xDai which use allow include [OmniBridge](https://omni.xdaichain.com/) and [HoneySwap](https://app.honeyswap.org/#/swap).

![Honeyswap allow example](../../.gitbook/assets/approve-example%20%282%29.png)

The safest practice is to allow only the amount you want to transfer currently, then repeat the allowance process each time. This is especially painless on xDai, where transaction costs are minimal. However, unlimited approval is often the default \(in the example above you would need to _Edit Permission_ to change\).

[Revoke.cash](https://revoke.cash/) provides a simple way to check your allowances and revoke them, or adjust them to lower amounts rather than unlimited allowances. It works on Ethereum and xDai.

## Basic Instructions

1\) Go to [Revoke.cash](https://revoke.cash) and connect your web3 \(MetaMask\) wallet. [Set MetaMask to the xDai chain](../wallets/metamask/metamask-setup.md).

![Connect your wallet](../../.gitbook/assets/revoke1.png)

2\) You address should populate and you can view any allowances you've granted for specific tokens. These are often related to bridge transactions or exchange transactions.

3\) To update an allowance, enter the amount of tokens to allow in the text box and click update. Then confirm the transaction in MetaMask.

![Updating an unlimited allowances to a smaller amount](../../.gitbook/assets/revoke2.png)

4\) To revoke, simply click revoke and confirm the MetaMask tx. _Note that MetaMask USD gas estimates are not accurate in this example, and that the cost is actually $0.000029._

![](../../.gitbook/assets/revoke3.png)

5\) Refresh the page to see your new allowances or check other addresses. You can also switch MetaMask to Ethereum to revoke allowances on Mainnet.

![](../../.gitbook/assets/revoke4.png)







