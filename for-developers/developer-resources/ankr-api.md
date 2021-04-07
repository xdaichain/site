---
description: Use Ankr to setup an Archive or Fast API endpoint
---

# Ankr API

Instant xDai API access is available with Ankr. The free tier includes up to 100K requests/day, and you can connect to a Nethermind Archive or Fast node with JSON RPC or Websockets. 

{% hint style="info" %}
For more information, see the [Ankr Docs](https://docs.ankr.com/)
{% endhint %}

## Setup

1\) Sign up for an account at [https://app.ankr.com/auth/sign-up](https://app.ankr.com/auth/sign-up). Once you are logged in, you will be directed to the dashboard. 

1. Select the Market Icon
2. Go to API Markets
3. Select xDai

![](../../.gitbook/assets/ankr-1.png)

2\) Enter a project name, network \(keep as mainnet\) and press next. This is for tracking and organizing your projects in the dashboard.

![](../../.gitbook/assets/ankr-2.png)

3\) Choose your authentication method. For basic authentication you will select a username and password. You can also use token authentication and a token is automatically created.

![](../../.gitbook/assets/ankr-4.png)

4\) Once you've created a project, you will see it in the API menu. Click on a project to view the details. 

![](../../.gitbook/assets/ankr3.png)

5\) On the details page you will see your API endpoint and wss link. Click on the copy icon to get the endpoint.

![](../../.gitbook/assets/ankr5.png)

## Querying the xDai Chain

### Example: `eth_blockNumber` query

This example uses token authentication with the copied API endpoint, so no need to specify username/password. We query the latest block number using the `eth_blockNumber` method and no parameters.

**Example Query:**

```text
curl -H "Content-Type: application/json" -d '{"id":1, "jsonrpc":"2.0", "method": "eth_blockNumber","params": []}' your-copied-api-endpoint
```

**Example Response:**

The query returns a hexadecimal response equal to the latest block number. We get `0xeb48e3`equal to `15419619`.

```text
{"jsonrpc":"2.0","result":"0xeb48e3","id":1}
```

### JSON-RPC methods <a id="json-rpc-methods"></a>

Additional info on methods:

* Eth Wiki: [https://eth.wiki/json-rpc/API](https://eth.wiki/json-rpc/API)
* Postman: [https://documenter.getpostman.com/view/4117254/ethereum-json-rpc/RVu7CT5J?version=latest](https://documenter.getpostman.com/view/4117254/ethereum-json-rpc/RVu7CT5J?version=latest)

