---
description: A first-hand account of the ETHDenver 2020 Burner Wallet & xDai experience
---

# ETHDenver 2020 xDai & Burner Wallet Recap

_**TL;DR**: **`DOGFOODING`** is good for you! When technology conferences embrace the technology they are touting, things break, participants glimpse the future, and hundreds of development hours are compressed into one intense weekend._

This year, xDai team representatives attended [ETHDenver 2020](https://www.ethdenver.com/) as both participants and volunteers. It was amazing to get a small peek behind the curtain from the volunteer table. As problems arose, the organizers, devs and volunteers were able to address issues head on and come up with creative, on-the-fly solutions.

After the event, we were particularly interested in learning more about how the Burner Wallet evolved from a simple click-and-pay system the previous year to a full-blown interactive conference navigation portal in 2020. The wallet included a map which showed participants where and how to collect experience \(XP\) points. These XP quests appeared dynamically throughout the event, and points were used at the end of the conference as votes on hackathon projects. The more a participant engaged with sponsors and collected points, the more pull they had in the final decision making process.

This is not to say that the process was smooth, or that the wallet integrations worked all the time. However, it was cool to witness and be a part of a conference that embraced new technology so readily, knowing full well it could break. Ultimately, conference organizers realized the outcome of these breaks, while difficult to deal with in the moment, would serve to push the technology forward much faster.

Once the conference wrapped up, and the post-conference ski break ⛷ was over, we caught up with [David Mihal](https://twitter.com/dmihal), a lead developer on this year’s Burner Wallet team and the creator of the [Burner Factory.](https://burnerfactory.com/) Along with [Austin Griffith](https://twitter.com/austingriffith) \(the man behind the original Burner Wallet\) and a dedicated team of volunteer devs, their team put together an amazing crypto experience for attendees in a very short period of time.

The following article highlights some moments from our conversation about the conference as well as our own observations about ETHDenver and the ethos of rapid prototyping experienced throughout the event.

![Austin Griffith and David Mihal presenting on the Burner Wallet at ETHDenver](https://gblobscdn.gitbook.com/assets%2F-Lpgb1NM7QPMRDExHay_%2F-M2-_9jrcBIyKC3fo-c3%2F-M2-elNhJRZpn64wrn87%2Faustin-and-david.png?alt=media&token=65dee191-7c69-4b77-bf5c-526781009f11)

## DAppy Hour <a id="dappy-hour"></a>

At 10:00pm Sunday night the [MakerDao](https://makerdao.com/) sponsored “DAppy Hour” was in full swing. DAppy Hour is the ETHDenver closing party and just like at the ETHDenver conference, participants were using a cryptocurrency called BuffiDai to purchase food and drinks.

Roughly 60 hours prior, on Friday morning, each of the 2000+ ETHDenver attendees had received a small amount of BuffiDai in their conference wallets. BuffiDai is the official ETHDenver conference currency; it is used for food purchases, swag purchases and charitable donations through the event. Any leftover BuffiDai is not usable after the conference, so DAppy Hour presents the final opportunity to liquidate.

As the evening progressed, some crypto transactions were not going through, and the crowd was getting restless and thirsty. Fortunately, developer David Mihal had a free hand \(the other was occupied by an IPA\). He opened his MacBook and started pushing bug fixes push faster than the drinks were going down. Disaster was averted, once again.

This wasn’t the first issue that occured with BuffiDai and Burner Wallets \(the official ETHDenver conference crypto wallet\) over the weekend. But rather than feeling upset or flustered, David was energized. Another bug had been identified and squashed! The Burner Wallet had undergone some severe stress testing, and hundreds of development hours had been compressed into one intense weekend.

## ETHDenver <a id="ethdenver"></a>

The ETHDenver hackathon presents an opportunity for the Ethereum community to come together for a weekend of creation and fast iteration on new blockchain applications. Participants are here to experiment and expectations are that things will break.

Rather than use time-tested or centralized tools, conference attendees embrace innovation and “dogfooding”, where the same new tools that conference sponsors are shilling are the tools that hackers are hacking on and conference organizers are using to run the conference.

One of these tools is the Burner Wallet \(BW\). Created by Austin Griffith and introduced to a large audience at ETHDenver 2019, the BW is a crypto wallet designed for mobile interaction. Participants can easily scan QR codes containing purchase amounts and an address, and BuffiDai is transferred almost instantaneously. A typical transaction takes 5 seconds.

Below the surface, the BW runs on the [xDai chain](http://xdaichain.com/), an Ethereum-based stable sidechain that provides extremely fast transaction speeds and low, known transaction costs. Because xDai is EVM compatible, any smart contracts or applications that can run on Ethereum can also run on xDai

At ETHDenver 2019, the sole purpose of the Burner Wallet was to process food purchases. It worked really well for conference attendees; BW is easy enough for crypto-newbies to use and provides a “dogfooding” experience for Ethereum veterans.

Drawing on this success, conference organizers and the dev team - which included David and Austin - created an extremely ambitious agenda for the Burner Wallet at ETHDenver 2020. And for the most part, they pulled it off.

![EthDenver Conference Burner Wallet](https://gblobscdn.gitbook.com/assets%2F-Lpgb1NM7QPMRDExHay_%2F-M0TvnBrWT3TPcE7bYTD%2F-M0Txihp1DwbAk7Ro_Ty%2Fbuffidao.png?alt=media&token=50fc2ef9-2aeb-4afd-8913-a8edc9bb21ee)

## The Burner Wallet DAO 

Plans for the Burner Wallet at ETHDenver started shaping up in mid-November 2019. This meant the team had roughly 3 months \(including the holiday break\) to put the entire project together. Not only would the wallet be completely redesigned, the functionality would vastly expand to include integrations with multiple 3rd party applications and a focus on community participation as a DAO. Food purchases would be included as well 🍕.

The concept of a DAO, or Decentralized Autonomous Organization, is a popular topic in the Ethereum community. DAOs provide a model for decentralized group governance where individuals are fairly represented within the collective. They can take many forms, but typically DAOs include:

1. A group of individuals who are connected through a common purpose, goal or interest.
2. Each individual provides a measure of collateral or “stake” to signal their interest and accountability to the DAO. Stake can be financial or another tangible asset \(like an amount of time tokenized into an asset\).
3. Stake gives individuals the opportunity to participate in DAO governance. This means they can propose new rules or ideas to the group and vote on other proposed measures. Often, the amount of stake determines how much voting power an individual in the group is afforded.
4. Decisions are typically recorded on-chain and may be enacted through smart contract functionality, depending on the nature of the DAO and the decisions being made.

ETHDenver wanted to create a DAO made up of the community members attending the event. Participants were already connected through a common purpose, and all had provided stake in the form of time and resources required to attend \(others had also staked actual ETH to support the community and receive swag\).

Participation was tokenized into XPs \(experience points\), and attendees were able to earn them by completing various tasks. Mostly, these involved engaging with sponsors. For example, participants could earn 25 XP by following [Quantstamp](https://quantstamp.com/) on Twitter, or 50 XP for staking into [PoolTogether](https://www.pooltogether.com/). To make this work, the Burner Wallet needed to dynamically display XP quests \(many were pushed throughout the event\) and provide an interface for earning and collecting points.

To power the governance and voting aspect, XP points could be used as hackathon votes \(and thus help determine the hackathon winners\) on the last day of the conference. In order to create this system, a host of integrations and a ton of collaboration would be required.

## Collaboration & Integration <a id="collaboration-and-integration"></a>

To start, the organizing team made a wishlist for the wallet with potential enhancements that would increase functionality and enable the DAO. Persistent wallet login would be useful, as BW keys are kept in local storage and can be easily lost. As would a human readable wallet address, an XP leaderboard, and lots of ⭐ awesome ⭐ real-time stats, and of course the DAO integration. Fortunately, the teams were in place to make this happen. Collaborating teams included:

* ​[Fortmatic](https://fortmatic.com/): Persistent login
* ​[DaoStack](https://daostack.io/): DAO voting / XP point integration
* ​[Unstoppable Domains](https://unstoppabledomains.com/): Human readable domain names, airdropped to all users
* ​[3Box](https://3box.io/): XP Leaderboard
* ​[Splunk](https://www.splunk.com/): Real time data visualization
* ​[TheGraph](https://thegraph.com/): DAOStack subgraph
* ​[xDai Chain](https://www.xdaichain.com/): Stable sidechain
* ​[WhiteBlock](https://whiteblock.io/): On-site infrastructure, including xDai and Gas Station Network nodes

Once the vision and collaborators were in place, it was up to the dev team to start designing and developing. And they needed to make it happen quickly, as it was now 2020, and ETHDenver was less than 6 weeks away.

![MakerDAO Donation Station - data graphics powered by Splunk](https://gblobscdn.gitbook.com/assets%2F-Lpgb1NM7QPMRDExHay_%2F-M2-_9jrcBIyKC3fo-c3%2F-M2-g7ye4s8fLBEIAkcW%2Fcharity.png?alt=media&token=0cc30831-4401-4731-b8e6-2c16f05d0e2c)

## PegaBufficorn <a id="pegabufficorn"></a>

For the final month, the devs feverishly wrote code, designed a flying PegaBufficorn logo \(the official mascot of the event\), broke things \(a lot\) and tested \(a bit\). The new enhancements and integrations made the 2019 Burner Wallet look quaint by comparison. Some missed the simple functionality, but everyone was ready to push the limits and see what this new system could accomplish.

As the weekend approached, fallback plans were made in case functionality didn’t work as expected. Some integrations were deployed the night before, with fingers crossed for the big event.

## Food Truck Dilemma <a id="food-truck-dilemma"></a>

The last thing the team thought would break was the food truck purchasing. After all, this was battle-tested and a bit of an afterthought with all of the new functionality. But, on the first day, a few attendees \(a small percentage of users\) couldn’t complete a food truck purchase. It didn’t matter that other things were working, they were getting hungry, and hacker food is the one thing you don’t want to mess with.

David went outside with a laptop, scanned the food truck QR code, and everything went through on his end. But it still wasn’t working for others. He gathered a bigger group who all scanned the QR code, but they couldn’t reliably replicate the issue.

Then he rounded up 10 “volunteers” who locked themselves in an upstairs room with a recreated QR code. They started feverishly scanning and sending transactions in different ways \(like upside down\) until something broke. Finally, they figured out that issues were happening when someone sent a transaction and then reloaded the page before it went through. This series of unfortunate clicks kept a transaction in a permanent pending state.

Due to the Fortmatic integration, the initialization process was throwing off the transaction processing. A quick fix was simple - disable the send button until Fortmatic was ready. Because the Burner Wallet is a web application, code could be pushed immediately and all users would instantly receive the fix. The problem was solved for users 10 minutes after the underlying issue was discovered.

Edge cases like these were uncovered several times during the event, and then fixed in the live setting. In a sense, all conference attendees were also volunteer testers, providing real-world feedback and discovering bugs in real time as the process unfolded.

![Food trucks in the AM, awaiting customers](https://gblobscdn.gitbook.com/assets%2F-Lpgb1NM7QPMRDExHay_%2F-M2-_9jrcBIyKC3fo-c3%2F-M2-eQxi7-tN3p6xVBUU%2FIMG_1700%202.JPG?alt=media&token=38344725-6a08-4f2b-aca2-a8dec04e20ad)

## Burner Wallet + <a id="burner-wallet"></a>

In addition to introducing new bugs, many new features also ended up working really well :\). An integration with [Gas Station Network](https://gasstation.network/) allowed users to submit transactions without paying any transaction costs. The previous year, each Burner wallet was airdropped several cents worth of xDai to cover costs, and an enterprising hacker found a way to drain some of these funds. This year, no gas was needed, and the relay network was amazingly robust.

The Burner Connect functionality also worked well - the wallet could connect to DAOStack and transfer XP tokens to the DAOStack environment without sharing private keys. This was a big step forward for Burner Wallet security as private keys could be kept private when interacting with other applications!

## Excited and Frightened at the Same Time <a id="excited-and-frightened-at-the-same-time"></a>

When David received the call in November about all of the proposed functionality for the Burner Wallet at ETHDenver 2020, he recalled feeling “really excited and really frightened at the same time”.

Considering the worst case scenarios that played out in his head, the event went off really well, and the excitement far outpaced the fear. A lot of this is thanks to the organizers and the community, who are accepting of potential issues and excited to serve as guinea pigs in these types of real-world crypto experiments.

In general, the blockchain community still inhabits the edges, attracting individuals who are future minded and driven to unseat some very entrenched power structures. These individuals are willing to take risks and break things in the service of long-term change and societal improvement.

At ETHDenver, these qualities were on full display, allowing for some amazing collaboration and innovation. The Burner wallet was a symbol of this collaborative spirit, and served as an appropriate gateway and compass for navigating the conference and the Ethereum ecosystem as a whole.

![Governors Jared Polis of Colorado and Mark Gordon of Wyoming talking cryptocurrency at ETHDenver](https://gblobscdn.gitbook.com/assets%2F-Lpgb1NM7QPMRDExHay_%2F-M2-_9jrcBIyKC3fo-c3%2F-M2-f1ifNQyqKR5Ib6o5%2Fpolis-and-.png?alt=media&token=270414a0-dfb4-4174-bc68-171116afb465)



