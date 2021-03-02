# xDai Rewards \(via Chai - currently deprecated\)

{% hint style="warning" %}
Update October 08 2020: **Chai conversion has been disabled through a governance vote. It was costing extra fees for users and the savings rate was set to 0 for a prolonged period. The governors may revisit at a later time or look to introduce another mechanism for incentivization.**  
  
[Proposal and Decision](https://forum.poa.network/t/disable-chai-token-support-to-safe-gas-for-deposit-and-withdrawal-operations/3936)
{% endhint %}

While the majority of rewards are paid in STAKE, additional stable incentives \(xDai\) are provided to stakers. These rewards are made possible by leveraging [Chai](http://chai.money), an ERC20 token created by the MakerDAO team. Chai generates risk-free interest from Dai. The interest is funded by Maker stability fees.

To provide stable rewards, Dai is locked in the bridge contract. xDai is minted on the xDai chain, and the locked Dai in the bridge is converted to Chai. Chai earns interest during this time. When a user requests to move xDai back to Dai, xDai is burned, Chai is converted back to locked Dai, and Dai is unlocked and returned to the user on the Ethereum Mainnet. The accumulated interest is distributed to stakers in xDai during the staking epoch.

Dai &lt;-&gt; Chai conversion is seamless and can occur at any point in time through function calls. Depending on the amount of Dai locked in the contract and the Chai interest rate, the amount of interest accrued will vary.

![Locked DAI is converted to interest-earning CHAI. Interest is distributed to stakers as rewards. Sai is no longer available to bridge..](https://gblobscdn.gitbook.com/assets%2F-Lpgb1NM7QPMRDExHay_%2F-M-Br-sb_fDiddcvfx8f%2F-M-ByVw_4RK6DryprPeZ%2FStakers%20%282%29.png?alt=media&token=c069f923-6c2c-49f2-b577-6cd3afef88e6)

