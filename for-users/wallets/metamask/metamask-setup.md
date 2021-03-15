---
description: Setup your custom RPC to connect to Metamask
---

# Metamask Setup

{% hint style="warning" %}
Note: Sending tokens to exchanges or other addresses you do not control may result in a loss of funds if the address is not supported by xDai. For example, sending tokens to Coinbase, Trustwallet, etc directly from the xDai network.

**Bridge to your address on Ethereum first, then transfer!**

* **xDai - Dai Bridge:** [http://bridge.xdaichain.com/](http://bridge.xdaichain.com/)
* **OmniBridge \(for all other ERC20 Tokens\):** [https://omni.xdaichain.com/](https://omni.xdaichain.com/)
{% endhint %}

## Setting up MetaMask for xDai

1\) Open Metamask, and select "Custom RPC" from the Network Dropdown.

![](../../../.gitbook/assets/custom-rpc.png)

2\) In the "Custom RPC" Settings, add in the xDai network details and click **Save**:

* Network Name: **xDai**
* New RPC URL: [**https://rpc.xdaichain.com/**](https://rpc.xdaichain.com/)
* Chain ID: **0x64**
* Symbol: **xDai**
* Block Explorer URL: [**https://blockscout.com/xdai/mainnet**](https://blockscout.com/xdai/mainnet/)

{% hint style="info" %}
Note: Chain ID 0x64 is the hexadecimal equivalent of 100, which is the xDai chain ID. MetaMask recently updated the ChainID to be a required field. When you update, you may need to reenter the Chain ID: 100, and it will be converted to a hexadecimal: 0x64**.**

**If you are having issues, try entering 100 for Chain ID and resaving the configuration.**
{% endhint %}

{% hint style="info" %}
If you'd prefer not to make these changes, [**Nifty Wallet** ](https://chrome.google.com/webstore/detail/nifty-wallet/jbdaocneiiinmjbjlgalhcelgbejmnid)provides a built-in xDai RPC.
{% endhint %}

{% hint style="success" %}
Once you add the xDai network, you will need xDai to pay for transactions. See [Getting xDai](../../get-xdai-tokens/) for more information.
{% endhint %}

## Connecting to a Hardware Wallet

Instructions for using MetaMask with a Ledger or Trezor: [https://metamask.zendesk.com/hc/en-us/articles/360020394612-How-to-connect-a-Trezor-or-Ledger-Hardware-Wallet](https://metamask.zendesk.com/hc/en-us/articles/360020394612-How-to-connect-a-Trezor-or-Ledger-Hardware-Wallet)

## Troubleshooting Issues

This [troubleshooting guide from 1Hive](https://forum.1hive.org/t/troubleshooting-problems-on-metamask/215) is helpful if you are experiencing issues with MetaMask and xDai.

