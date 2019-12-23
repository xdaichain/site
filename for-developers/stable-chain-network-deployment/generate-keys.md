# 8\) Generate Keys

1\) Create 3 initial keys on the  `Master of Ceremony` node using the scripts from [https://github.com/poanetwork/poa-scripts-moc/tree/core](https://github.com/poanetwork/poa-scripts-moc/tree/core):

```text
git clone https://github.com/poanetwork/poa-scripts-moc.git
cd poa-scripts-moc
```

2\) Modify `KEYS_MANAGER_ADDRESS` in poa-network-consensus-contracts/contracts.json and the abi \[\] section \(poa-network-consensus-contracts/build/contracts/KeysManager.json\) of the `KeysManager` contract inside the root `config.json` file.

* Set `gasPrice` to `0` in `generateInitialKey/utils/addInitialKey.js`

```diff
diff --git a/generateInitialKey/utils/addInitialKey.js b/generateInitialKey/utils/addInitialKey.js
index 0dadf4d..0c6e02f 100644
--- a/generateInitialKey/utils/addInitialKey.js
+++ b/generateInitialKey/utils/addInitialKey.js
@@ -28,8 +28,8 @@ function addInitialKey(contract, initialKey, MoC) {

 //sends tx to activate initial key
 function addInitialKeyTX(contract, initialKey, estimatedGas, MoC) {
-    let opts = {from: MoC, gasLimit: estimatedGas}
+    let opts = {from: MoC, gasLimit: estimatedGas, gasPrice: "0"}
     return contract.methods.initiateKeys(initialKey).send(opts);
 }
```

* Comment out the code for sending a small amount of coins to initial keys in `generateInitialKey/utils/sendEtherToInitialKeyTX.js`

```diff
diff --git a/generateInitialKey/utils/sendEtherToInitialKeyTX.js b/generateInitialKey/utils/sendEtherToInitialKeyTX.js
index 87ba634..1cb4392 100644
--- a/generateInitialKey/utils/sendEtherToInitialKeyTX.js
+++ b/generateInitialKey/utils/sendEtherToInitialKeyTX.js
@@ -1,6 +1,8 @@
 //sends tx to transafer 0.1 eth from master of ceremony to initial key
 function sendEtherToInitialKeyTX(web3, initialKey, MoC) {
        return new Promise((resolve, reject) => {
+                resolve();
+/*
                let BN = web3.utils.BN;
                let ethToSend = web3.utils.toWei(new BN(100), "milliether");
                console.log(`WEI to send to initial key: ${ethToSend}`)
@@ -17,7 +19,8 @@ function sendEtherToInitialKeyTX(web3, initialKey, MoC) {
                .on("error", (err) => {
                        reject(err);
                });
+*/
        })
 }
```

* Launch `generateInitialKey/index.js`

  ```text
  cd generateInitialKey
  node index.js #Repeat as many times as needed. Each run will generate a new key
  ```

{% hint style="info" %}
The generated keys \(json keystores and their passwords\) will be saved into the `output` directory.
{% endhint %}

3\) The `Master of Ceremony` adds initial keys into the `Certifier` contract so that each validator can complete a transaction registering the primary keys \(mining + voting + payout\).

Call the `certify` method with `_who = 0xINITIAL_KEY_ADDRESS` for each initial key [using the MyCrypto method.](5-reconfigure-instances.md#call-contract-methods-using-mycrypto)

