---
description: Update json.spec files and launch Register & Certifier contracts
---

# 5\) Reconfigure MoC Instance

{% hint style="success" %}
Start here after [initial instance configuration](4-configure-instances.md).
{% endhint %}

## Master of Ceremonies \(MoC\) Instance Initial Steps

1\) Login to MoC instance and go to the `moc` directory

```text
ssh -i ubuntu@moc-ec2-user.DNS/Address
```

```text
ubuntu@ip-moc-ec2-user:~ cd ../moc
```

2\) Replace the existing `spec.json` file, changing parameters as required:

1. Copy [https://raw.githubusercontent.com/poanetwork/poa-chain-spec/dai-deployment/spec.json](https://raw.githubusercontent.com/poanetwork/poa-chain-spec/dai-deployment/spec.json)
2. `sudo nano spec.json` paste and make changes as needed:

* `name` must be `{{ network_name }}`
* `engine.authorityRound.params.blockReward` must be `0x0`
* `engine.authorityRound.params.validators.multi.0.list` must contain the `Master of Ceremony` address
* `params.networkID` must be a unique ID for your network. &lt;[See a list of current ids](https://ethereum.stackexchange.com/questions/17051/how-to-select-a-network-id-or-is-there-a-list-of-network-ids)&gt;
* `genesis.gasLimit` - change if needed

3\) Adjust the `node.toml` file on **MoC** with the following settings:  
_\(we use nano in this demonstration, feel free to use vim or another editor of your choice\)_

```text
sudo nano node.toml
```

* `parity.chain` must be a path to `spec.json`
* `account.unlock` must contain the `Master of Ceremony` address. \(do not uncomment yet\)
* `mining.min_gas_price` is a min gas price in Wei
* `mining.engine_signer` must contain the `Master of Ceremony` address
* `mining.gas_floor_target` is a max block size in gas

4\) Launch the `Master of Ceremony` node

```text
sudo systemctl restart poa-parity && sleep 10 && sudo systemctl restart poa-netstats
```

## Prepare `Register` & `Certifier` Contracts

1\) Clone [https://github.com/parity-contracts/name-registry](https://github.com/parity-contracts/name-registry) repository

```text
sudo git clone https://github.com/parity-contracts/name-registry
cd name-registry
```

* Set `gasPrice` to `0` in `truffle-config.js`. Replace port 7545 with Port 8545.

```diff
    diff --git a/truffle-config.js b/truffle-config.js
    index ee5a576..62681ac 100644
    --- a/truffle-config.js
    +++ b/truffle-config.js
    @@ -4,8 +4,9 @@ module.exports = {
       networks: {
         development: {
           host: "127.0.0.1",
    -      port: 7545,
    +      port: 8545,
           network_id: "*",
    +      gasPrice: "0"
         },
       },
     };
```

* Unlock Master of Ceremony in `node.toml`. 
  * `cd..` to moc directory
  * `sudo nano node.toml`
  * Uncomment \#`unlock=[...]`
  * Restart Parity: `sudo systemctl restart poa-parity && sleep 10 && sudo systemctl restart poa-netstats`

2\) Deploy Contracts

```text
cd name-registry
sudo npm i
sudo node_modules/.bin/truffle migrate --reset --network development
```

{% hint style="success" %}
Deployment artifacts will be stored in the `build` subfolder.
{% endhint %}

{% hint style="info" %}
If you experience issues with npm install, you can use yarn. Instructions here: [https://yarnpkg.com/lang/en/docs/install/\#debian-stable](https://yarnpkg.com/lang/en/docs/install/#debian-stable)
{% endhint %}

## Update bootnodes.txt

You need to write the current MoC's `enode` to the `bootnodes.txt` file.

1\) Run this command on the MoC node to retrieve the current enode

```text
curl --data '{"method":"parity_enode","params":[],"id":1,"jsonrpc":"2.0"}' -H "Content-Type: application/json" -X POST localhost:8545
```

2\) Copy the json result

3\) `sudo nano bootnodes.txt`

4\) Replace the default enodes with the current enode and save.

```text
enode://your-enode-here:30303
```

## Copy Items before exiting

* `spec.json` file - you will replace the Bootnode instance with this file. Example:

```text
scp -i ~/.ssh/your-private-key ubuntu@moc-ec2-user.DNS/Address:/home/moc/spec.json your-local-folder/
```

* Addresses of the newly deployed `Certifier` and `Registry` contracts. Go to the `name-registry` subdirectory and execute:

```text
grep -Rn \"address\": build/contracts/{SimpleCertifier.json,SimpleRegistry.json} 
```

* `bootnodes.txt` file - you will replace the Bootnode instance with this file.

{% hint style="success" %}
Next: [Configure Bootnode](6-configure-bootnode-instance.md)
{% endhint %}



