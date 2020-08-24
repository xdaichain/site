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

| Resource | URL |
| :--- | :--- |
| JSON RPC endpoint  | [https://xdai.poanetwork.dev](https://xdai.poanetwork.dev/) |
| WebSockets WSS endpoint | [wss://xdai.poanetwork.dev/wss](wss://xdai.poanetwork.dev/wss) |

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

A bridge is required to move locked Dai from Ethereum and mint xDai on xDai Chain

You can access the bridge via:

* TokenBridge UI at [https://dai-bridge.poa.network](https://dai-bridge.poa.network)
* Interactions with Smart contracts[ ](https://docs.tokenbridge.net/xdai-bridge/how-to-use-xdai-bridge-without-ui)[https://docs.tokenbridge.net/xdai-bridge/how-to-use-xdai-bridge-without-ui](https://docs.tokenbridge.net/xdai-bridge/how-to-use-xdai-bridge-without-ui)
* Bridge UI built-in into AlphaWallet, BurnerWallet, BurnerFactory

## DApp Management & Developer Tools

* [Biconomy](https://medium.com/biconomy/biconomy-supports-xdai-chain-4d21d1f70222) allows for for gasless transactions and improved DApp UX.
* [Pocket](https://www.pokt.network/) provides a decentralized API layer for DApp developers \(IOS, Android & Web SDKs available\) and blockchain users.
* [TheGraph](https://thegraph.com) supports xDai data indexing, querying and display.
* [Chainbeat](https://chainbeat.io/) provides monitoring and analytics tools for DApp developers.
* [BlockNative](https://docs.blocknative.com/) supports real-time notification monitoring with API and SDK tools.
* [Token faucet](https://erc20faucet.com/) allows you to easily create ERC20 FAU tokens for testing purposes
* [Tenderly](https://tenderly.co/) dashboard supports xDai transaction inspection - smart contracts can also be pushed to the dashboard for real-time monitoring.
* [QuikNode](https://www.quiknode.io/) gives users a super-fast Web3 endpoint for accessing or interacting with the xDai chain.
* [CurveGrid](https://www.curvegrid.com/) provides smart contract deployment, interaction and updating capabilities  through a web UI as well as a comprehensive REST API.
* [3Box](https://www.3box.io/):  Externally Owned Account \(EOA\) addresses are the same on xDai as they are on other EVM networks, so no changes are needed to implement 3box functionality.

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

