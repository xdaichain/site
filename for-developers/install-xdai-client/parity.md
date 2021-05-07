---
description: xDai with POSDAO runs on OpenEthereum v3.0.0
---

# OpenEthereum \(formerly Parity\)

## Install OpenEthereum

{% hint style="warning" %}
Please update to `v3.2.5` which contains Berlin hard fork transition and the new enodes: [https://github.com/openethereum/openethereum/releases/tag/v3.2.5](https://github.com/openethereum/openethereum/releases/tag/v3.2.5)

Perform a DB migration if your run OE version &lt; v3.2.0

If your node works on an old version of Parity, you need to convert node's DB to the format compatible with OpenEthereum v3.2.x. You can use this tool [https://github.com/openethereum/3.1-db-upgrade-tool](https://github.com/openethereum/3.1-db-upgrade-tool)
{% endhint %}

{% hint style="success" %}
_For a non-dev user friendly version, see_ [_https://forum.1hive.org/t/run-your-own-local-xdai-node/2875_](https://forum.1hive.org/t/run-your-own-local-xdai-node/2875)_. Note this uses the previous version_ 3.0.1 - clients should now run v3.2.5
{% endhint %}

### Binary Instructions

{% hint style="info" %}
These instructions are copied from the [OpenEthereum wiki.](https://openethereum.github.io/Setup)
{% endhint %}

* **Linux**
  * Download the latest release from the link above
  * Make the openethereum file executable by running `chmod u+x openethereum`
  * Launch OpenEthereum: `./openethereum --chain xdai --no-warp`

{% hint style="info" %}
The `--no-warp` flag is recommended if you want all historical data, but will take much longer to sync. For a faster sync, you do not need to use it. [More information on --no-warp](https://openethereum.github.io/Beginner-Introduction.html)
{% endhint %}

* Mac
  * Download the mac binary.
  * Open a terminal and navigate to the directory using `cd /path/to/binary/folder/`.
  * Make the binary executable by running `chmod +x openethereum`.
  * You can now double click on the binary. 
* Windows Download the binary and double click on it.

### Dependencies <a id="dependencies"></a>

For Linux systems:

* Ubuntu, Debian

  ```text
    $ apt-get install build-essential cmake libudev-dev
  ```

* CentOS

  ```text
    $ yum install libudev-devel
    $ yum group install "Development Tools"
  ```

## Once OpenEthereum is Installed, Connect and Sync with xDai

```text
openethereum --chain xdai --no-warp
```

#### Optional

`--no-warp` flag is optional: [more information.](https://openethereum.github.io/wiki/Getting-Synced)

_If you would like to limit or choose specific bootnodes, you can obtain the bootnodes.txt file from POA github:_

```bash
git clone -b dai https://github.com/poanetwork/poa-chain-spec.git
```

enter all supplied enodes for the desired network separated by a comma, no space

```text
openethereum --chain xdai --bootnodes enode://ENODE@IP:PORT,enode://ENODE@IP:PORT
```

### Connect to your Node

You can use [Ethereum's JSON-RPC ](https://openethereum.github.io/JSONRPC)or a JavaScript console.

### Smart contract development

You can use [Remix](https://remix.ethereum.org/) connected to a local OpenEthereum full node for smart contracts development and deployment. Make sure that Remix is allowed to connect to your node by setting up the right [JSON-RPC cors policy](https://ethereum.stackexchange.com/questions/54639/is-it-possible-to-connect-remix-and-parity?rq=1).

