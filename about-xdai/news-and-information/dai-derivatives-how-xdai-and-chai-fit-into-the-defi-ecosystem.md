# Dai Derivatives: How xDai \(& Chai\) fit into the DeFi ecosystem

DeFi \(Decentralized Finance\) is reshaping the blockchain landscape. It is open, trustless, and provides financial transparency while preserving security. DeFi is still in it’s infancy, with many new users and use cases onboarding daily. In light of the current crises facing nations and the banking industry, decentralized currencies and stable currencies are needed now more than ever.

The Dai stable coin, by [MakerDAO](https://makerdao.com/), is one of the anchors of the DeFi movement. Dai is pegged to the US dollar and maintains this stability through overcollateralization of multiple onchain currencies. Though they have [experienced recent issues](https://forum.makerdao.com/t/black-thursday-response-thread/1433), the project remains strong and continues to be resilient despite growing pains. 

Since Dai was introduced, a large number of Dai derivatives have been created with different use cases in mind.  xDai was the original Dai derivative, created to support a stable chain where transactions could be completed with a single token \(on the mainnet you must spend Ether for gas when transacting Dai\). It also moved transactions off of the mainnet, reducing congestion, optimizing capacity, and providing a platform for micro-transactions.

xDai is created by locking Dai into a bridge contract. The same amount of xDai is then minted on the xDai chain. In reverse, xDai is burned and the original Dai is unlocked back on the mainnet. 

![A line at Bank of Ethereum](../../.gitbook/assets/levi-jones-n0ctq0rroso-unsplash.jpg)

We may think of the Ethereum blockchain as an awesome trustless, _**`PERMISSIONLESS`**_ bank run by and for the people, but sometimes there is still a line \(sometimes short, sometimes winding around the block!\). You can pay to get closer to the front of the line, wait for a while….. or you can use the xDai chain - an ATM with no line at all. 

xDai is designed for lightning fast transactions with known, stable fees. The [Burner Wallet](../../for-users/wallets/burner-wallet.md), a prominent xDai UI, is designed for carrying small amounts of xDai - just like the $40 you get from the ATM on your way to a night on the town. Other use cases demand different interfaces, and wallets like [AlphaWallet](../../for-users/wallets/alpha-wallet/) & [Portis](../../for-users/wallets/portis-wallet.md) provide more advanced features as needed.

Beyond xDai, other Dai derivatives are designed to capture additional interest for the user.[ cDai](https://defipulse.com/blog/what-is-cdai/), [rDai](https://rdai.money/) and others use decentralized lending protocols to pool and loan Dai and capture interest in return.

With the POSDAO transition, xDai will incorporate an interest earning derivative called [Chai](https://chai.money/). Chai tokenizes the Dai Savings Rate \(DSR\), so that the value of each Chai grows according to that rate. With this new model, the Dai locked in the bridge contract \(it is locked to create xDai\) will be converted to Chai, and immediately start earning interest.

![](../../.gitbook/assets/stakers-2.png)

When a user wants to exit the xDai chain \(move their xDai back to Dai on the mainnet\), Chai is converted back to Dai. The Dai they locked is redeemed, and the interest earned on that Dai is distributed as a reward to xDai stakers \(validators and delegators\).

POSDAO presents the opportunity to leverage several Dai derivatives on the xDai chain. This is how DeFi is meant to operate - models can be created and iterated by combining, discarding or reforming the existing building blocks into something entirely new.  For a comprehensive list of Dai derivatives in production and in development, see [https://github.com/jordanlyall/dai-universe](https://github.com/jordanlyall/dai-universe)

