---
description: Sending transactions from a validator's mining address
---

# Mining Address Usage

A validator's mining address will accumulate xDai over time. However, due to limitations placed on mining addresses, it is not possible to call additional contract functions from this address \(like the bridge contract\). If you want to bridge xDai to Dai, first send it to another external address. 

Because mining addresses are used for randomness txs, the nonce is increased once every 3 minutes. If you are experiencing problems with sending a transaction to another address, the nonce may have become obsolete and the transaction will need to be sent with an actual nonce. You can reset your nonce in MetaMask using the Reset Account feature in **Settings** -&gt; **Advanced** and toggle **Customize Transaction Nonce.** This will enable you to update the nonce.









