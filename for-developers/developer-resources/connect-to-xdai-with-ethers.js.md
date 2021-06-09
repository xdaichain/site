# Connect to xDai with Ethers.js

[ethers.js](https://github.com/ethers-io/ethers.js/) is a lightweight javascript library that can be used as an alternative to web3.js for blockchain interaction and development. It is open-source and easy to work with. Here we use ether.js with xDai to complete a simple query on the xDai chain. 

{% hint style="info" %}
Instructions adapted from a [quicknode guide](https://www.quicknode.com/guides/web3-sdks/how-to-connect-to-ethereum-network-with-ethers-js).
{% endhint %}

1\) Make sure you have node.js installed. If not, [install on your system](https://nodejs.org/en/).

```text
$ node -v
```

2\) Install ethers.js using NPM

```text
$ npm install --save ethers
```

_**Common issues:**_ 

* node-gyp failure \([installation instructions](https://github.com/nodejs/node-gyp#installation)\). Check that your python version is compatible w/instructions above. 
* stale cache. Clear your npm cache with the `npm cache clean` command.

3\) Connect to xDai via ethers. You can copy/paste this script into your own code editor. Save this file as `index.js`

```text
var ethers = require('ethers');  
var url = 'https://rpc.xdaichain.com/';
var customHttpProvider = new ethers.providers.JsonRpcProvider(url);
customHttpProvider.getBlock(16488144).then((result) => {
    console.log("Block Info: " + JSON.stringify(result, null, 4));
});
```

_**Notes:**_

* This example uses the xDai public RPC. Feel free to use any working node rpc for var url = `https://rpc.xdaichain.com/`
* `getBlock` returns an object for the specified block number \(16488144\), so we use JSON.stringify to print results to the console.

4\) Run the script & see the results!

```text
$ node index.js
```

**Output**

```text
Current block: {
    "hash": "0xd19228f8e38621769cd51de5d33e5a0660d241fdddce3f6f545a5d1c2c2e3281",
    "parentHash": "0x354db1b35390f5bc83dba5cec0acf2b5aca2b38eba3f9797753872eb17cebf88",
    "number": 16488144,
    "timestamp": 1623262980,
    "difficulty": null,
    "gasLimit": {
        "type": "BigNumber",
        "hex": "0x01036640"
    },
    "gasUsed": {
        "type": "BigNumber",
        "hex": "0x123ef8"
    },
    "miner": "0xb76756f95A9fB6ff9ad3E6cb41b734c1bd805103",
    "extraData": "0x4e65746865726d696e64",
    "transactions": [
        "0xaf98291e33762314013337c2bf84a56447b3d2f2d3f157e65a23d30d548ac4b6",
        "0xaebb11d6c662d704096584d4b2dc6ba6187975c078c071f37244eb6453196b89",
        "0xb8f8c379c64fd746d35a3aa915993773ced054d6026331c071c5e05172e04d1a",
        "0x26fd0732013f34d962c48e9b6d74ffe5eb0ac4497f63e80f9be3a077dde60636",
        "0x5cf6acd7a397e276464340f3cebae03e8939b5980820eb1605a825ced72b72c8",
        "0x9e4fc47ba538f7f15a21be1974ffe759e005329425952f1e0d3dfc4a77b99057",
        "0x139eee70febe9b4514d4f2f5966d7e01adb08be88658949758aabe000a5aa4e3",
        "0xc66e4dae09619b5943c9a84cede691122cc10e0cd833b09063a850c94f5a78b8"
    ]
}
```

{% hint style="success" %}
ether.js documentation is [available here](https://docs.ethers.io/v5/).

For more detailed information, see the [quiknode guide](https://www.quicknode.com/guides/web3-sdks/how-to-connect-to-ethereum-network-with-ethers-js).

To start diving into development with ethers.js, try this quick tutorial from [Zastrin](https://medium.com/zastrin/build-an-ethereum-dapp-using-ethers-js-c561f9c4dd2f).
{% endhint %}

