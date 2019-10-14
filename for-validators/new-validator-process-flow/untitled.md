---
description: 'To begin, validators create necessary accounts and announce their candidacy'
---

# Validator Candidate

##  1. Post Introduction to Forum

Post a short introduction about yourself and why you want to become a validator on the forum [https://forum.poa.network/c/xdai-chain/validators-intro](https://forum.poa.network/c/xdai-chain/validators-intro).

##  2. Generate up to 4 Ethereum Accounts

1. **Mining key** to validate blocks on the network. The mining key will be used on network validator node running parity, so it’s required that you have the json keystore file \(and password to decrypt it\).
2. **Voting key** to participate in voting/governance. Can be stored on your hardware wallet \(ledger/trezor\)
3. **Payout key** to collect tx fee reward. Can be stored on your hardware wallet \(ledger/trezor\)
4. **Bridge validator key \[optional - only for validators who are also becoming bridge validators\]** for use on the bridge validator node, it is required that you have the private key for this account.

### **Generate the Mining key, Voting key, and Payout key**

The POA Ceremony DApp provides a convenient interface to get all 3 keys. If you would prefer, you can use a different tool to generate your keys.

1. In MetaMask or Nifty Wallet connect to xDAI chain RPC endpoint \(RPC URL = [https://dai.poa.network](https://dai.poa.network), network ID = 100\)
2. Go to [https://ceremony.poa.network/\#just-generate-keys](https://ceremony.poa.network/#just-generate-keys)
3. A zip file with key information should be automatically downloaded to your computer. If this is not the case, manually copy each address and password, matching them to the correct section \(Mining, Payout, Voting\).

{% hint style="info" %}
#### Store this information securely, preferably on an encrypted drive \(e.g. usb drive\). If keys are lost, you must have your old keys voted out and new ones voted in.
{% endhint %}

### **\[Optional\] Generate the Bridge Validator Account**

Create a new account and export and save the private key. Use your preferred method to create a key pair. MyCrypto, MetaMask, etc. allow you to easily create and download a private key.

###  3. \[Optional\] Fund the Bridge Account  <a id="heading--3"></a>

_If you are also becoming a bridge validator_, send a small amount of ETH \(eg 1 ETH\) to the bridge validator account you just created. The balance should be monitored and a minimal amount continuously stored at this address for bridge operations. If preferred, you can wait on this step until after you have been confirmed as a new validator.

###  4. Announce your Addresses <a id="heading--4"></a>

Announce your generated addresses in the forum, you can post the public \(no private info!\) addresses here. Current validators will then have this information, and one of them can create a ballot to elect you as a new validator.  
[https://forum.poa.network/c/xdai-chain/validators-intro](https://forum.poa.network/c/xdai-chain/validators-intro)

{% hint style="warning" %}
[Node configuration](new-xdai-validator-node-setup.md) occurs after your are elected as a validator
{% endhint %}

## Next Steps

The [Current Validators](current-xdai-validators-ballot-process.md) will create a ballot to vote on your candidacy. If you are elected, they will inform you through the forum and you will proceed to the [Node setup phase](../node-deployment/).

