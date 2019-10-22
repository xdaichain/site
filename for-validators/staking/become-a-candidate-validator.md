# Become a Candidate / Validator

{% hint style="warning" %}
This page is currently under construction
{% endhint %}

Validators are responsible for securing the xDai stable chain. Validator responsibilities include maintaining a functional node with constant uptime, providing STAKE as collateral, and providing decentralization to the protocol. In exchange for this service, validators receive block rewards and transaction fees.

To become a validator on the xDai stable chain, you must first become a candidate. Each staking epoch, 19 candidate pools are chosen to act as validators for that epoch. If there are 19 or fewer active candidates, then all active pools are selected. If there are more than 19, selection is based on total stake in the pool + a random number. [See this article for more info on weighting and randomness](https://forum.poa.network/t/reliable-randomness-bringing-on-chain-entropy-to-the-xdai-stable-chain/3015).

{% hint style="info" %}
If you do not want to become a validator, but are interested in placing stake on other validators, see Become a Delegator
{% endhint %}

#### Instructions:

1\) You will need the minimum candidate stake amount of STAKE and a small amount of xDAI deposited to your address on the xDai chain. Deposit these to your staking address - this is the address you will use to access the protocol. 

2\) In addition to your regular staking address, you will need a separate mining address which will be configured to a Parity node. Generate and save the json keystore file \(and be sure to save the password in a safe place!\) 

> Note: Do we want a validator key generator for xDai? Otherwise can create here under keystore tab: https://www.myetherwallet.com/create-wallet

3\) Setup your node:

> Confirm current instructions are correct for new stake-basedv alidators

* AWS
* Non-AWS

4\) Once your node is setup and ready, go to [blockscout.com ](http://blockscout.com/)and change the Network to the xDai network. `<screenshot>`

5\) After you have switched to xDai, select an item from the Stakes dropdown. `<screenshot>`

6\) Set your web3wallet \(Metamask/Nifty\) account to your Staking address and network to xDai. Once connected, you should see your address and $DPOS balance in the site banner.

![](../../.gitbook/assets/candidate_1.png)

7\)  Click the **Become a Candidate** button in the header. You will see this modal.

![](../../.gitbook/assets/candidate_2.png)

8\) Select the amount of STAKE you would like to place as your initial stake \(you can always add additional stake later\) and enter your mining address from step 2.

9\) Click **Become a Candidate**. Submit and complete the transaction through the web3 wallet interface.

10\) f successful, your pool will appear in the Active Pools tab. You will be eligible to join the next staking epoch as a Validator! If there are more than 19 candidates, you will be chosen based on the total stake amount in your pool \(your stake + any delegators stake\) plus a random number.

