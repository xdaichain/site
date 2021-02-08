---
description: General Information and Links
---

# Developer Resources & Tools

## General Information

| Block Size | Block Speed | Gas price | Patchset | Native token | Network ID |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 12,500,000 Gas | 5 sec | 1 GWei | Istanbul | xDai | 100 |

## Blockchain Explorer

1\) **BlockScout** is the official blockchain explorer for the xDai Chain. With this full-featured, open-source explorer you can view transactions, accounts & balances, access data via the API, and read and verify smart contracts.

👉 [https://blockscout.com/poa/xdai](https://blockscout.com/poa/xdai)

2\) **AnyBlock Analytics Explorer** is convenient for exploring recent transactions and blocks and locating common information quickly**.**

👉 [https://explorer.anyblock.tools/ethereum/poa/xdai/](https://explorer.anyblock.tools/ethereum/poa/xdai/)

## JSON RPC endpoints

Main RPC is a load balancer with 4 nodes, health checks, and failover. 

<table>
  <thead>
    <tr>
      <th style="text-align:left">Resource</th>
      <th style="text-align:left">URL</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">JSON RPC endpoint</td>
      <td style="text-align:left">
        <p><a href="https://rpc.xdaichain.com/">https://rpc.xdaichain.com/</a>
        </p>
        <p>(alternative) <a href="https://xdai.poanetwork.dev/">https://xdai.poanetwork.dev</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">WebSockets WSS endpoint</td>
      <td style="text-align:left">
        <p><a href="wss://rpc.xdaichain.com/wss">wss://rpc.xdaichain.com/wss</a>
        </p>
        <p>(alternative) <a href="wss://xdai.poanetwork.dev/wss">wss://xdai.poanetwork.dev/wss</a>
        </p>
      </td>
    </tr>
  </tbody>
</table>

Additional resources to connect to xDai network

| Resource | URL |
| :--- | :--- |
| JSON RPC endpoint over HTTP \(non-secure\) | [http://xdai.poanetwork.dev](http://xdai.poanetwork.dev/) |
| JSON RPC endpoint via Cloudflare | [https://dai.poa.network](https://dai.poa.network) |
| WebSockets WS \(non-secure\) | [ws://xdai.poanetwork.dev:8546](ws://xdai.poanetwork.dev:8546) |
| Archive node | [https://xdai-archive.blockscout.com](https://xdai-archive.blockscout.com/) |
| Network ID | 100 |

🚀 QuikNode also supports xDai. Devs can get their own custom endpoint for DApps or other needs. [https://blog.quiknode.io/xdai-network-is-live-on-quiknode/](https://blog.quiknode.io/xdai-network-is-live-on-quiknode/)

## TokenBridge

There are two bridge implementations connecting xDai and the Ethereum Mainnet. 

\*\*\*\*[**xDai Bridge**](https://docs.tokenbridge.net/xdai-bridge/about): ERC20-to-Native TokenBridge implementation, used for transferring Dai &lt;-&gt; xDai between Ethereum and the xDai chain.

\*\*\*\*[**ETH-xDai Arbitrary Message Bridge**](https://docs.tokenbridge.net/eth-xdai-amb-bridge/about-the-eth-xdai-amb): AMB between Ethereum and xDai for data, token and message transfers. Includes the Ominibridge application for transfer of any ERC20 cross-chain.

#### xDai Bridge Access

* xDai Bridge UI at [https://dai-bridge.poa.network](https://dai-bridge.poa.network)
  * Interaction using method calls for smart contracts[ ](https://docs.tokenbridge.net/xdai-bridge/how-to-use-xdai-bridge-without-ui)[https://docs.tokenbridge.net/xdai-bridge/how-to-use-xdai-bridge-without-ui](https://docs.tokenbridge.net/xdai-bridge/how-to-use-xdai-bridge-without-ui)
* Bridge UI is built-in into AlphaWallet, BurnerWallet, BurnerFactory and other applications.

#### OmniBridge Access 

* [OmniBridge UI](https://xdai-omnibridge.web.app/). More information [including method calls here.](https://docs.tokenbridge.net/eth-xdai-amb-bridge/multi-token-extension)

## DApp Management & Developer Tools

{% hint style="info" %}
See the dropdown menu for tutorials related to some of these tools.
{% endhint %}

* [Biconomy](https://medium.com/biconomy/biconomy-supports-xdai-chain-4d21d1f70222) allows for gasless transactions and improved DApp UX.
* [TheGraph](https://thegraph.com) supports xDai data indexing, querying and display.
* [QuikNode](https://www.quiknode.io/) gives users a super-fast Web3 endpoint for accessing or interacting with the xDai chain.
* [Pocket](https://www.pokt.network/) provides a decentralized API layer for DApp developers \(IOS, Android & Web SDKs available\) and blockchain users.
* [CurveGrid](https://www.curvegrid.com/) provides smart contract deployment, interaction and updating capabilities through a web UI as well as a comprehensive REST API.
* [3Box](https://www.3box.io/):  Externally Owned Account \(EOA\) addresses are the same on xDai as they are on other EVM networks, so no changes are needed to implement 3box functionality.
* [BlockNative](https://docs.blocknative.com/) supports real-time notification & transaction monitoring with API and SDK tools.
* [Sourcify](https://sourcify.dev/) Smart Contract Source Verification. Contracts can also be verified with [BlockScout](%20https://blockscout.com/poa/xdai).
* [Remix IDE](https://remix-project.org/):  It's easy to deploy to xDai with Remix, simply choose injected web3 and add the [xDai custom RPC to your metamask](https://www.xdaichain.com/for-users/wallets/metamask/metamask-setup).

### **Dashboards & Monitoring**

* [Dune Analytics](https://www.duneanalytics.com/): Dune supports xDai for data queries and custom dashboards. Visualize and compare data between contracts and chains \(xDai and Ethereum support\)
* [Tenderly](https://tenderly.co/) dashboard supports xDai transaction inspection - smart contracts can also be pushed to the dashboard for real-time monitoring.
* [Chainbeat](https://chainbeat.io/) provides monitoring and analytics tools for DApp developers.
* [Dappquery](https://dappquery.com/) analytics dashboard, customizable visualizations, smart contract alerts and scalable GraphQL API.

###  **Token Faucets**

**xDai Faucet**

* [https://blockscout.com/poa/xdai/faucet](https://blockscout.com/poa/xdai/faucet) An xDai faucet to quickly get .01 xDai and start using the chain right away! 

**Test Token Faucets**

* [Token faucet](https://erc20faucet.com/) allows you to easily create ERC20 FAU tokens for testing purposes.
* [Weenus ERC20 ](https://github.com/bokkypoobah/WeenusTokenFaucet)is also available to use for testing purposes.

![Tenderly Dashboard Gas Profiler example](../../.gitbook/assets/tenderly.png)

## **Additional Resources**

**General Migration Guide:** A fun and easy xDai migration guide from DAOHaus: [https://medium.com/daohaus-club/daohaus-xdai-dapp-migration-83dca1fc590a](https://medium.com/daohaus-club/daohaus-xdai-dapp-migration-83dca1fc590a)

Tutorial on how to use GasRelay in your Dapp by Portis. With a few lines of code, gas fees are shifted to DApp owners rather than users, creating an intuitive user experience.  
[https://docs.portis.io/\#/gas-relay](https://docs.portis.io/#/gas-relay)

WebSockets Endpoint \(can be useful to setup BlockScout for xDai\)  
[wss://dai-trace-ws.blockscout.com/ws](wss://dai-trace-ws.blockscout.com/ws)

Archive Fullnode Endpoint \(Useful for setting up BlockScout for xDai\)  
[https://dai-trace-ws.blockscout.com](https://dai-trace-ws.blockscout.com)

Chain [spec](https://github.com/poanetwork/poa-chain-spec/blob/dai/spec.json) files and known [bootnodes](https://github.com/poanetwork/poa-chain-spec/blob/dai/bootnodes.txt) of the xDai network  
[https://github.com/poanetwork/poa-chain-spec/tree/dai](https://github.com/poanetwork/poa-chain-spec/tree/dai)

Netstats, an overview of xDai Chain nodes [http://dai-netstat.poa.network](http://dai-netstat.poa.network/)

DApps Deployed to xDai: Partial list of deployed DApps along with statistics and links: [https://www.stateofthedapps.com/rankings/platform/xdai](https://www.stateofthedapps.com/rankings/platform/xdai)

xDai is available in the Anyblock Index \(aka [http://eth.events](http://eth.events)\), so you can query it via the Elasticsearch API or search in PostgreSQL: [https://account.anyblock.tools/status/](https://account.anyblock.tools/status/)

