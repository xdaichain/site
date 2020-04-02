---
description: xDai with POSDAO runs on the Parity 2.7.2 stable version
---

# OpenEthereum \(formerly Parity\)

{% hint style="info" %}
While Parity is now OpenEthereum, there are still overlaps in documentation and download resources that link to Parity docs. When OpenEthereum v3 stable is released many of these redundancies should be accounted for.
{% endhint %}

### Ubuntu/Debian & MacOS with Homebrew: one-line Binary Installation

This method is for Ubuntu/Debian based OS and MacOS machines with Homebrew installed. Faster than building from source, but no cutting edge features or latest version. If you would like to build from [source](https://github.com/paritytech/parity) or download binary release, see the official [2.7.2 Release Page.](https://github.com/openethereum/openethereum/releases/tag/v2.7.2) The xDai network is supported by  `Parity` stable version 2.7.2.

Open a bash Terminal and enter the command below, if the client needs an update just simply run the command a second time.  

```bash
bash <(curl https://get.parity.io -kL)
```

This will install and configure the Parity client for you. On Ubuntu, this script will also offer to install the Netstats client and connect it to ethstats.net. If you plan on using `Parity` for xDai only, there is no need to install the extra software. 

### **Install using Linux distro Snap Service**

```text
sudo snap install parity --edge
```

### Install Parity on Windows

Parity on Windows can either be installed as a System Service or executed from a folder. The executable file is available on  [OpenEtherum Parity 2.7.2 release page](https://github.com/openethereum/openethereum/releases/tag/v2.7.2).

{% hint style="info" %}
More information related to Parity setup and configuration is available on the Parity wiki. [https://wiki.parity.io/Setup](https://wiki.parity.io/Setup)
{% endhint %}

### Once Parity is Installed,  Connect and Sync with xDai

1. Download the latest spec.json file from [https://raw.githubusercontent.com/poanetwork/poa-chain-spec/dai/spec.json](https://raw.githubusercontent.com/poanetwork/poa-chain-spec/dai/spec.json)
2. Run the following command specifying the correct path to the spec.json file downloaded in step 1.

```text
parity --chain ./spec.json --no-warp
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

You can use Ethereum's JSON-RPC or a JavaScript console: [https://wiki.parity.io/Basic-Usage](https://wiki.parity.io/Basic-Usage)

Parity's UI is deprecated, but information on the site provides alternatives to a local Parity Ethereum node: [https://wiki.parity.io/Parity-Wallet](https://wiki.parity.io/Parity-Wallet)

