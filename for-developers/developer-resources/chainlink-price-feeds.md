---
description: Chainlink Integrations allows access to price feeds on xDai
---

# Chainlink Price Feeds

Chainlink allows smart contracts to receive aggregated price feeds and access external data using a decentralized network of oracles. The xDai &lt;-&gt; Chainlink integration was completed by [Protofire with a Chainlink Community Grant.](https://blog.chain.link/protofire-receives-a-chainlink-community-grant-for-an-integration-with-xdai/) 

{% hint style="info" %}
Chainlink offers a tutorial on using secure data feeds with xDai. [See it in action](https://blog.chain.link/build-a-dapp-on-xdai-chain-with-secure-data-feeds/) 🏃♂ 
{% endhint %}

## Addresses

* **Link Token on xDai**: [`0xE2e73A1c69ecF83F464EFCE6A5be353a37cA09b2`](https://blockscout.com/poa/xdai/address/0xE2e73A1c69ecF83F464EFCE6A5be353a37cA09b2)\*\*\*\*
* **Price Feeds on xDai:** _Latest list is available in the_ [_Chainlink Documentation_](https://docs.chain.link/docs/xdai-price-feeds)_._

| Pair | Decimals | Proxy Contract |
| :--- | :--- | :--- |
| AAVE / USD | 8 | [`0x2b481Dc923Aa050E009113Dca8dcb0daB4B68cDF`](https://blockscout.com/poa/xdai/address/0x2b481Dc923Aa050E009113Dca8dcb0daB4B68cDF) |
| BAL / USD | 8 | [`0x1b723C855F7D2c2785F99486973271355e782d77`](https://blockscout.com/poa/xdai/address/0x1b723C855F7D2c2785F99486973271355e782d77) |
| BTC / USD | 8 | [`0x6C1d7e76EF7304a40e8456ce883BC56d3dEA3F7d`](https://blockscout.com/poa/xdai/address/0x6C1d7e76EF7304a40e8456ce883BC56d3dEA3F7d) |
| CRV / USD | 8 | [`0xC77B83ac3Dd2a761073bD0f281f7b880B2DDDe18`](https://blockscout.com/poa/xdai/address/0xC77B83ac3Dd2a761073bD0f281f7b880B2DDDe18) |
| DAI / USD | 8 | [`0x678df3415fc31947dA4324eC63212874be5a82f8`](https://blockscout.com/poa/xdai/address/0x678df3415fc31947dA4324eC63212874be5a82f8) |
| DOT / USD | 8 | [`0x3c30c5c415B2410326297F0f65f5Cbb32f3aefCc`](https://blockscout.com/poa/xdai/address/0x3c30c5c415B2410326297F0f65f5Cbb32f3aefCc) |
| ETH / USD | 8 | [`0xa767f745331D267c7751297D982b050c93985627`](https://blockscout.com/poa/xdai/address/0xa767f745331D267c7751297D982b050c93985627) |
| LINK / USD | 8 | [`0xed322A5ac55BAE091190dFf9066760b86751947B`](https://blockscout.com/poa/xdai/address/0xed322A5ac55BAE091190dFf9066760b86751947B) |
| PERP / USD | 8 | [`0x76e76F7E73F3BD42E3c2b4282B50b36E78130B4A`](https://blockscout.com/poa/xdai/address/0x76e76F7E73F3BD42E3c2b4282B50b36E78130B4A) |
| SNX / USD | 8 | [`0x3b84d6e6976D5826500572600eB44f9f1753827b`](https://blockscout.com/poa/xdai/address/0x3b84d6e6976D5826500572600eB44f9f1753827b) |
| SUSHI / USD | 8 | [`0xC0a6Bf8d5D408B091D022C3C0653d4056D4B9c01`](https://blockscout.com/poa/xdai/address/0xC0a6Bf8d5D408B091D022C3C0653d4056D4B9c01) |
| UNI / USD | 8 | [`0xd98735d78266c62277Bb4dBf3e3bCdd3694782F4`](https://blockscout.com/poa/xdai/address/0xd98735d78266c62277Bb4dBf3e3bCdd3694782F4) |
| USDC / USD | 8 | [`0x26C31ac71010aF62E6B486D1132E266D6298857D`](https://blockscout.com/poa/xdai/address/0x26C31ac71010aF62E6B486D1132E266D6298857D) |
| YFI / USD | 8 | [`0x14030d5a0C9e63D9606C6f2c8771Fc95b34b07e0`](https://blockscout.com/poa/xdai/address/0x14030d5a0C9e63D9606C6f2c8771Fc95b34b07e0) |

## Basic Tutorial: Price Feeds

See the [Chainlink documentation](https://docs.chain.link/docs/getting-started) for more advanced tutorials and information. The following shows how to use MetaMask/Remix with xDai to deploy a simple price feed contract, then call the function using Blockscout.

### 1\) Switch to xDai RPC in MetaMask

Go to MetaMask, select Custom RPC from the network dropdown, and enter the following details. If you need more info, see [MetaMask Setup](../../for-users/wallets/metamask/metamask-setup.md).

* Network Name: xDai 
* New RPC URL: [https://rpc.xdaichain.com/](https://rpc.xdaichain.com/) 
* Chain ID: 0x64 
* Symbol: xDai 
* Block Explorer URL: [https://blockscout.com/poa/xdai](https://blockscout.com/poa/xdai)

### 2\) Get xDai with Faucet

You can get enough xDai to deploy your contracts and more with the xDai Faucet. Go to [https://blockscout.com/poa/xdai/faucet](https://blockscout.com/poa/xdai/faucet) to request .01 xDai. You should see it added to your address in a few seconds.

### 3\) Open Remix and Create File

Go to [https://remix.ethereum.org/](https://remix.ethereum.org/)

There are several ways to create a new file. Here we:

1. Create a folder called xDai Price Feed.
2. Create a file in the folder called `PriceFeedTest.sol`.
3. Paste in the example code below the image.

![](../../.gitbook/assets/chain1%20%281%29.png)

### Example Code

```text
/** This example code is designed to quickly deploy an example contract using Remix.
 *  If you have never used Remix, try our example walkthrough: https://docs.chain.link/docs/example-walkthrough
 *  You will need xDai to deploy.
 *     - xDai Faucet: https://blockscout.com/poa/xdai/faucet
 *     - LINK address on xDai: 0xE2e73A1c69ecF83F464EFCE6A5be353a37cA09b2
 */

pragma solidity ^0.6.7;

import "https://github.com/smartcontractkit/chainlink/blob/master/evm-contracts/src/v0.6/interfaces/AggregatorV3Interface.sol";

contract PriceConsumerV3 {

    AggregatorV3Interface internal priceFeed;

    /**
     * Network: xDai
     * Aggregator: ETH/USD
     * Address: 0xa767f745331D267c7751297D982b050c93985627
     */
    constructor() public {
        priceFeed = AggregatorV3Interface(0xa767f745331D267c7751297D982b050c93985627);
    }

    /**
     * Returns the latest price
     */
    function getLatestPrice() public view returns (int) {
        (
            uint80 roundID, 
            int price,
            uint startedAt,
            uint timeStamp,
            uint80 answeredInRound
        ) = priceFeed.latestRoundData();
        return price;
    }
}
```

The code below uses the Chainlink standard Price Consumer contract along with several modifications:

* We initialize the ETH/USD xDai Price Feed in the constructor

```text
priceFeed = AggregatorV3Interface(0xa767f745331D267c7751297D982b050c93985627);
```

We use the `getLatestPrice` function to return the current price. It pulls this from the `latestRoundData` function in the imported `AggregatorV3Interface.sol` Contract 

### 4\) Compile Contract in Remix

Click on the Compiler Icon, adjust items \(if necessary, we keep defaults here\) and click the Compile button.

![](../../.gitbook/assets/chain2%20%281%29.png)

### 5\) Deploy Contract 

1. Select Deploy Icon.
2. Change Environment to Web3.
3. Click Deploy.
4. Confirm the transaction in MetaMask. You account must be connected to the xDai chain and have a small amount of xDai \(see steps 1 and 2\).

![](../../.gitbook/assets/chain3%20%281%29.png)

### 6\) Check Contract

Once deployed, click to expand the contract. Click `getLatestPrice` to check the ETH/USD price.

![](../../.gitbook/assets/chainlin-4.png)

## Verify Contract in BlockScout Block Explorer

### 1\) Find Deployed Contract

For transparency and interaction purposes, you can verify your contract on [BlockScout](https://blockscout.com/poa/xdai). _Note, if a contract with the same bytecode has already been deployed and verified, your contract code may be viewable._ [_See this example_](https://blockscout.com/poa/xdai/address/0x681ef0446AA72723256f1De4d1BE7Dd9bb7F84Cf/contracts)_._

1. Copy the deployed contract address in Remix.
2. Go to [BlockScout](https://blockscout.com/poa/xdai) and paste into the search field.
3. Click the Code tab for verification methods.
4. Click the **Verify and Publish** Button.

![](../../.gitbook/assets/chain5.png)

![](../../.gitbook/assets/chain6.png)

![](../../.gitbook/assets/chain7.png)

### 2\) Add Sources to Verify

Select either a flattened file or Sources. In this example we select the Sources and metadata JSON files from Remix

![](../../.gitbook/assets/chain8.png)

Remix does not have an auto-export feature. You can use the [`remixd`](https://ethereum.stackexchange.com/questions/60115/how-to-save-solidity-remix-ethereum-file-in-local-disk-with-sol-extensionhow-to) or copy the contents of each file and save in a text editor computer using the same names and file extensions. **Include all imported files called by the contract**, in this case the `AggregatorV3Interface.sol` file.

![](../../.gitbook/assets/chain9.png)

 Drag and drop the files into the interface and click **Verify & publish**.

![](../../.gitbook/assets/chain10.png)

### 3\) View your Contract in BlockScout

Once verified, you will see the checkmark next to the code, and you can read \(and write\) to your contract within the BlockScout environment.

![](../../.gitbook/assets/chain11.png)

