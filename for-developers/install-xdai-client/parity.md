---
description: xDai with POSDAO runs on OpenEthereum v3.0.0
---

# OpenEthereum \(formerly Parity\)

## Install OpenEthereum

You can  build from source or download a binary release, see the official [3.0 Releases Page](https://github.com/openethereum/openethereum/releases) for download information for Linux, Mac & Windows.

### Binary Instructions

{% hint style="info" %}
These instructions are copied from the OpenEthereum wiki at [https://openethereum.github.io/wiki/Setup](https://openethereum.github.io/wiki/Setup)
{% endhint %}

* **Linux**
  * Download the latest release from the link above
  * Make the `parity` file executable by running `chmod u+x parity`
  * Launch Parity Ethereum: `./parity --chain xdai --no-warp`
* Mac
  * Download the mac binary.
  * Open a terminal and navigate to the directory using `cd /path/to/binary/folder/`.
  * Make the binary executable by running `chmod +x parity`.
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

## Once Parity is Installed,  Connect and Sync with xDai

```text
parity --chain xdai --no-warp
```

#### Optional

_If you would like to limit or choose specific bootnodes, you can obtain the bootnodes.txt file from POA github:_

```bash
git clone -b dai https://github.com/poanetwork/poa-chain-spec.git
```

enter all supplied enodes for the desired network separated by a comma, no space

```text
parity --chain xdai --bootnodes enode://ENODE@IP:PORT,enode://ENODE@IP:PORT
```

### Connect to your Node

You can use Ethereum's JSON-RPC or a JavaScript console:  
[https://openethereum.github.io/wiki/Basic-Usage](https://openethereum.github.io/wiki/Basic-Usage)

### Smart contract development

You can use [Remix](https://remix.ethereum.org/) connected to a local Parity Ethereum full node as an alternative to Parity UI for smart contracts development and deployment. Make sure that Remix is allowed to connect to your node by setting up the right [JSON-RPC cors policy](https://ethereum.stackexchange.com/questions/54639/is-it-possible-to-connect-remix-and-parity?rq=1).

