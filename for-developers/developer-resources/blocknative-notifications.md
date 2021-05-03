---
description: Blocknative supports xDai with real-time notification tools
---

# Blocknative Notifications

Blocknative provides tools to access a real-time data feed as transactions are added to the transaction pool/queue and moved to blocks. This includes mempool streaming and other offerings from BlockNative.

Developers and users can follow data using webhooks and access tools and resources for integrating these features into their DApps. Tools include an API, SDK and javascript library.  BlockNative also provides an Onboard tool DApp devs can integrate for wallet integration. **The xDai Network is supported by all of their tooling.**

## Resources

* BlockNative Docs: [https://docs.blocknative.com/](https://docs.blocknative.com/)
* Quickstart video tutorials: [https://www.youtube.com/channel/UC9engR8mowKMratKYMBzOXQ](https://www.youtube.com/channel/UC9engR8mowKMratKYMBzOXQ)

## Example: Add address notifications with API / Webhooks & Slack 

In this example we setup Slack notifications. For instructions on adding to a DApp or developing with BlockNative tools, see the [BlockNative docs](https://docs.blocknative.com/).

1\) Sign up for a Blocknative account on [https://account.blocknative.com](https://account.blocknative.com). Account creation requires an email confirmation.

2\) Create an API key for your application.

1. Go to API Keys in the Dashboard.
2. Enter a name for this key \(you can create additional keys later\).
3. Click **Generate New API Key.**

![](../../.gitbook/assets/api-keys.png)

3\) Go to Slack and add the **Incoming Webhooks**. Search for Apps and add the integration. Instructions: [https://api.slack.com/messaging/webhooks](https://api.slack.com/messaging/webhooks).   
Once enabled and added to a channel of your choice, **copy the Webhook url.**

![](../../.gitbook/assets/img2-copyurl.png)

4\) Return to Blocknative dashboard and click **Add a Webhook**. Fill in the following:

* URL \(from step 3\)
* Blockchain: Ethereum
* Network: xdai
* Username \(optional\)
* Password \(optional\)
* Click **Create New Webhook** button

![Enter details to create a new Webhook ](../../.gitbook/assets/img3.png)

5\) Add an address\(es\) to monitor.

1. Click Watch Address.
2. Enter an 0x address to watch \(can be a regular address, smart contract etc\).
3. Click **Watch**. Address will be added. You can add multiple addresses / smart contract addresses if desired.

![](../../.gitbook/assets/img4.png)

6\) Submit a transaction to test.

1. Submit a transaction with MetaMask or another wallet of your choice using the address you added in step 5
2. Go to Slack to see pending and confirmed tx data. The following is example confirmed data \(truncated\) received from a basic send transaction. See the [BlockNative Webhook API docs for all payload details](https://docs.blocknative.com/webhook-api#ethereum-notifications) for token transfer and contract method call transactions.

```text
{
  "status": "confirmed",
  "network": "xdai",
  "hash": "0x0.....2",
  "from": "0x...80",
  "to": "0x...e5",
  "value": "300000000000000000",
  "gas": 21000,
  "gasPrice": "33000000000",
  "blockHash": "0x...2",
  "blockNumber": 10...39,
  "input": "0x",
  "gasUsed": "21000",
  "asset": "ETH",
  "watchedAddress": "0x...80",
  "direction": "outgoing",
  "counterparty": "0x...e5",
  "apiKey": "53...7"
}
```





