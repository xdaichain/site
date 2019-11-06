# Parity

### Ubuntu/Debian & MacOS with Homebrew: one-line Binary Installation

This method is for Ubuntu/Debian based OS and MacOS machines with Homebrew installed. Faster than building from source, but no cutting edge features or latest version. If you would like to build from [source](https://github.com/paritytech/parity) or download binary release, see the official [Parity Releases Page](https://github.com/paritytech/parity/releases). The xDai network is supported by  `Parity` stable versions 2.5.8+, and beta versions 2.6.3+. 

Open a bash Terminal and enter the command below, if the client needs an update just simply run the command a second time.  

```
bash <(curl https://get.parity.io -kL)
```

This will install and configure the Parity client for you. On Ubuntu, this script will also offer to install the Netstats client and connect it to ethstats.net. If you plan on using `Parity` for xDai only, there is no need to install the extra software. 

### **Install using Linux distro Snap Service**

```
sudo snap install parity --edge
```

### Install Parity on Windows

Parity on Windows can either be installed as a System Service or executed from a folder. The executable file is available on  [Parity's Releases Page](https://github.com/paritytech/parity/releases). 

{% hint style="info" %}
More information related to Parity setup and configuration is available on the Parity wiki. [https://wiki.parity.io/Setup](https://wiki.parity.io/Setup)
{% endhint %}

### Once Parity is Installed,  Connect and Sync with xDai

```
parity --chain xdai --no-warp
```

#### Optional

_If you would like to limit or choose specific bootnodes, you can obtain the bootnodes.txt file from POA github:_

```
git clone -b dai https://github.com/poanetwork/poa-chain-spec.git
```

enter all supplied enodes for the desired network separated by a comma, no space

```
parity --chain xdai --bootnodes enode://ENODE@IP:PORT,enode://ENODE@IP:PORT
```

### Connect to your Node

You can use Ethereum's JSON-RPC or a JavaScript console: [https://wiki.parity.io/Basic-Usage](https://wiki.parity.io/Basic-Usage)

Parity's UI is deprecated, but information on the site provides alternatives to a local Parity Ethereum node: [https://wiki.parity.io/Parity-Wallet](https://wiki.parity.io/Parity-Wallet)

