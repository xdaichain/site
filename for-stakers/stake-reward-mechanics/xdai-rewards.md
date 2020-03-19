# xDai Rewards

While the majority of rewards are paid in STAKE, additional stable incentives \(xDai\) are provided to stakers. These rewards are made possible by leveraging [CHAI,](https://chai.money/) an ERC20 token created by the MakerDAO team. CHAI generates risk-free interest from DAI. The interest is funded by Maker stability fees.

To provide stable rewards, DAI or SAI is locked in the bridge contract. xDai is minted on the xDai chain, and the locked DAI in the bridge is converted to CHAI. CHAI earns interest during this time. When a user requests to move xDai back to DAI, xDai is burned, CHAI is converted back to locked DAI, and DAI is unlocked and returned to the user on the Ethereum Mainnet. The accumulated interest is distributed to stakers in xDai during the staking epoch.

DAI &lt;-&gt; CHAI conversion is seamless and can occur at any point in time through function calls. Depending on the amount of DAI locked in the contract, the amount of interest will vary, and can grow quite large if xDai Chain usage continues to expand.

![Locked DAI is converted to interest-earning CHAI. Interest is distributed to stakers as rewards.](https://gblobscdn.gitbook.com/assets%2F-Lpgb1NM7QPMRDExHay_%2F-M-Br-sb_fDiddcvfx8f%2F-M-ByVw_4RK6DryprPeZ%2FStakers%20%282%29.png?alt=media&token=c069f923-6c2c-49f2-b577-6cd3afef88e6)

