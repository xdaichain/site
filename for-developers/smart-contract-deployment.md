---
description: Follow the same process as deploying to Ethereum or the POA Network
---

# Smart Contract Deployment

The xDai Stable Chain is an EVM based chain, meaning deployment steps are the same as deployment to Ethereum, POA Network or other chains. The required changes consist of directing deployment to the xDai RPC and network id.

* **RPC:** [https://xdai.poanetwork.dev](https://xdai.poanetwork.dev) \([more RPCs available here](developer-resources/#json-rpc-endpoints)\)
* **Network\_ID:** 100

You will also need a [small amount of xDai ](../for-users/get-xdai-tokens/)to deploy a contract, and for any contract functions. There is no current xDai testnet, so your contracts will be live! For testing purposes, **it is recommended to first deploy to POA Sokol testnet**. After functionality is tested and confirmed, deploy to the xDai chain!

## Truffle Based Tutorial

[This tutorial on Kauri](https://kauri.io/#collections/POA%20Tutorial%20series/poa-part-1-develop-and-deploy-a-smart-contract/) shows how to deploy a DApp to the POA Sokol test network. It can be adapted to the xDai network with a few minor tweaks.

1\) For xDai, edit the truffle.js file to the following:

```javascript
require('dotenv').config();
const HDWalletProvider = require('truffle-hdwallet-provider');

module.exports = {
  // See <http://truffleframework.com/docs/advanced/configuration>
  // for more about customizing your Truffle configuration!
  networks: {
    xdai: {
          provider: function() {
                return new HDWalletProvider(
               process.env.MNEMONIC,
               "https://dai.poa.network")
          },
          network_id: 100,
          gas: 500000,
          gasPrice: 1000000000
    },
    development: {
          host: "127.0.0.1",
          port: 8545,
          network_id: "*" // Match any network id
    }
  }
};
```

2\) Run the truffle deployment to the xDai chain.

```text
truffle migrate --network xdai
```

## Remix Tutorial

This tutorial uses Nifty Wallet or MetaMask and Remix to deploy to POA Sokol. To change the deployment chain, simply select \(or configure with MetaMask\) the xDai chain. To view your transactions on xDai, use [BlockScout for xDai](https://blockscout.com/xdai/mainnet).

👩💻 [Remix Tutorial](https://forum.poa.network/t/tutorial-deploying-your-dapp-to-poa-network/1804)

