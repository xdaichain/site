---
description: A tool to revoke or adjust contract allowances
---

# Revoke

Many DeFi apps require users to `allow` a contract to spend funds before transfers are sent. This can result in an unlimited allowance, which carries security risks if a contract is compromised, has a bug, or if there are other issues. It is best practice to allow only the amount you want to transfer and repeat this process each time. This is especially true on xDai, where transaction costs are minimal.

[Revoke.cash](https://revoke.cash/) provides a simple way to check your allowances and revoke them, or adjust them to lower amounts rather than unlimited allowances. It works on Ethereum and xDai.

1\) Go to Revoke.cash and connect your web3 \(MetaMask\) wallet. [Set MetaMask to the xDai chain](../wallets/metamask/metamask-setup.md).

![Connect your wallet](../../.gitbook/assets/revoke1.png)

2\) You address should populate and you can view any allowances you've granted for specific tokens. These are often related to bridge transactions or exchange transactions.

3\) To update an allowance, enter the amount of tokens to allow in the text box and click update. Then confirm the transaction in MetaMask.

![Updating an unlimited allowances to a smaller amount](../../.gitbook/assets/revoke2.png)

4\) To revoke, simply click revoke and confirm the MetaMask tx. _Note that MetaMask USD gas estimates are not accurate in this example, and that the cost is actually $0.000029._

![](../../.gitbook/assets/revoke3.png)

5\) Refresh the page to see your new allowances or check other addresses. You can also switch MetaMask to Ethereum to revoke allowances on Mainnet.

![](../../.gitbook/assets/revoke4.png)







