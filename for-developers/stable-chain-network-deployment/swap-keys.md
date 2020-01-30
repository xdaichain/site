# 12\) Swap & Distribute Keys

{% hint style="info" %}
This process can also be performed by launching the`Ceremony DApp` with or without forking the `poanetwork/poa-chain-spec` repo. See [Appendix C: Governance DApps ](appendix-c-governance-dapps.md)for more info.
{% endhint %}

## Swap keys without forking

1\) Clone the  `Ceremony DApp` repo:

```text
$ git clone https://github.com/poanetwork/poa-dapps-keys-generation
$ cd poa-dapps-keys-generation
```

2\) Make `src/addresses.js` use the address of your `KeysManager` contract

```diff
diff --git a/src/addresses.js b/src/addresses.js
index 799909e..08c195e 100644
--- a/src/addresses.js
+++ b/src/addresses.js
@@ -1,15 +1,15 @@
 import { constants } from "./constants";
 import helpers from "./helpers";
-//const local = {
-//    "KEYS_MANAGER_ADDRESS": "0x3ef32bb244016ad9af8c8f45398511e7e551b581"   
-//}
+const local = {
+    "KEYS_MANAGER_ADDRESS": "0xKEYS_MANAGER"
+}

 export default (web3Config) => {
     const branch = constants.NETWORKS[web3Config.netId].BRANCH;
     return new Promise((resolve, reject) => {
         fetch(helpers.addressesURL(branch)).then((response) => { 
             response.json().then((json) => {
-                resolve({addresses: json, web3Config});
+                resolve({addresses: local, web3Config});
             })
         }).catch(function(err) {
             let addr = helpers.addressesURL(branch);
```

* Make `src/helpers.js` use the ABI of your `KeysManager` contract:

  ```text
  diff --git a/src/helpers.js b/src/helpers.js
  index 23b2399..af8ee58 100644
  --- a/src/helpers.js
  +++ b/src/helpers.js
  @@ -28,6 +28,7 @@ function ABIURL(branch, contract) {
   }

   function getABI(branch, contract) {
  +  if (contract == 'KeysManager') return [...ABI...];
     let addr = ABIURL(branch, contract);
     return fetch(addr).then(function(response) {
         return response.json();
  ```

* Launch DApp. Validators should use it to swap their initial keys to mining+voting+payout keys.

For testing purposes the script from [https://github.com/poanetwork/deployment-terraform/tree/master/helper-scripts/gen-prod-keys](https://github.com/poanetwork/deployment-terraform/tree/master/helper-scripts/gen-prod-keys) can be used:

* Edit `helper-scripts/gen-prod-keys/index.js` in the following manner:

  ```text
  diff --git a/helper-scripts/gen-prod-keys/index.js b/helper-scripts/gen-prod-keys/index.js
  index 5266629..ed0802d 100644
  --- a/helper-scripts/gen-prod-keys/index.js
  +++ b/helper-scripts/gen-prod-keys/index.js
  @@ -16,7 +17,7 @@ const keysManagerABI = require('./KeysManager.abi.json');
   var keysManagerContract;
   var chainId;

  -const GASPRICE_GWEI = 2;
  +const GASPRICE_GWEI = 0;

   function loginf(...args) {
       console.log(new Date().toISOString(), ...args);
  @@ -68,11 +69,13 @@ function getInitialKey(address) {
   }

   function checkInitialKey(address, next) {
  -    keysManagerContract.methods.getInitialKey(`0x${address}`).call((err, result) => {
  +    keysManagerContract.methods.getInitialKeyStatus(`0x${address}`).call((err, result) => {
           if (err) throw err;
           return next(result.toString());
       });
  ```

* Replace `KeysManager.abi.json` with abi\[\] part from `poa-network-consensus-contracts/build/contracts/KeysManager.json` \([example](https://github.com/poanetwork/deployment-terraform/blob/master/helper-scripts/gen-prod-keys/KeysManager.abi.json)\).
* Put initial keys into `keystore` subdirectory.
* Call the script for each key once per block:

{% hint style="info" %}
Replace `https://<rpc.endpoint>` with address of your bootnode with externally enabled RPC \(When running from `MoC` node you can skip entering `RPC_ENDPOINT` variable\) and `0xKEYS_MANAGER_ADDRESS` with keys manager address \(find it at `poa-network-consensus-contracts`**/**`contracts.json`\) 
{% endhint %}

```text
$ RPC_ENDPOINT=https://<rpc.endpoint> node index.js 0xKEYS_MANAGER_ADDRESS
```

{% hint style="info" %}
The primary keys \(mining+voting+payout\) will be saved into the `production-keys` subdirectory grouped by initial key
{% endhint %}

**Example:**

```text
production-keys/
├── validator-2ec2104bc1d45f9faa6d8218c7186222bb2388e5
│   ├── initial_2ec2104bc1d45f9faa6d8218c7186222bb2388e5.json
│   ├── initial_2ec2104bc1d45f9faa6d8218c7186222bb2388e5.key
│   ├── mining_1272b1cea9c5214d6d5ab9152edc7a96f70b3111.json
│   ├── mining_1272b1cea9c5214d6d5ab9152edc7a96f70b3111.key
│   ├── payout_c1ae3c98189564f671649affcd777d5eefda2c2b.json
│   ├── payout_c1ae3c98189564f671649affcd777d5eefda2c2b.key
│   ├── voting_25d54934564b82be18a32e16be2b0bc6337164f1.json
│   └── voting_25d54934564b82be18a32e16be2b0bc6337164f1.key
└── validator-38dd91a11dbd81a6a177d94cfa391dfa771631c8
...
```

{% hint style="warning" %}
It is important that you don't just convert all initial keys without launching validator nodes \(see next step\). It's best to convert one key, then launch corresponding validator node and make sure it's mining, then return to this step and convert the next key, launch second validator node, and so on. Otherwise, you may encounter bugs.
{% endhint %}

## Configure Validator Nodes

{% hint style="info" %}
Repeat this process for each validator node
{% endhint %}

1\) Distribute generated mining keys to validator nodes.

* Place `0x<address>.json` file into `parity_data/keys/$NetworkName/`
* Change the password in `node.pwd` \(take it from the corresponding `*.key` or `*.txt` generated file\)
* Change the address in `node.toml` \(replace `unlock = […]` and `engine_signer = "..."` lines with mining key address\).

2\) Configure `poa-scripts-validator` directory on each validator node:

* Set an address and ABI of `KeysManager` contract in the root [`config.json`](https://github.com/poanetwork/poa-scripts-validator/blob/88c38fbe41a74c1fbdadb6f3030eebb3d0991064/config.json#L9-L10) file.
* Set zero gas price in `poa-scripts-validator/transferRewardToPayoutKey/transferRewardToPayoutKey.js`.

  Find [the line](https://github.com/poanetwork/poa-scripts-validator/blob/88c38fbe41a74c1fbdadb6f3030eebb3d0991064/transferRewardToPayoutKey/transferRewardToPayoutKey.js#L92)

  ```text
  var gasPrice = web3.utils.toWei(big('1'), 'gwei');
  ```

  and replace with

  ```text
  var gasPrice = web3.utils.toWei(big('0'), 'gwei');
  ```

3\) Change validators `INSTANCE_NAME` in `/home/validator/eth-net-intelligence-api/app.json` if necessary. 

4\) Update `bootnodes.txt` with the `bootnodes.txt` file from the Bootnode instance. It will contain 2 lines the first time you run this process, one enode for the MoC node and the second for the Bootnode.

4\) Start validator's node.

```text
sudo systemctl restart poa-parity && sleep 10 && sudo systemctl restart poa-netstats
```

5\) Check that the node is synchronized with the MoC and Bootnode nodes.

Open [http://1.2.3.4:3000](http://1.2.3.4:3000/) \(using your Netstats url instance\) to check your nodes.

6\) Repeat process for remaining Validator nodes.

{% hint style="success" %}
Next: [Finalize Deployment](10-finalize-deployment.md)!
{% endhint %}

