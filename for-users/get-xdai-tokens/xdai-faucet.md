---
description: Different ways to obtain small amounts of xDai
---

# xDai Faucets

## OmniBridge Faucet Script

The OmniBridge faucet script now automatically deposits a small amount of xDai \($0.005\) to users bridging tokens from Ethereum or BSC. This is enough to start making transactions. If more is needed, bridged tokens can be [swapped on a DEX](../../about-xdai/project-spotlights/#defi) for additional xDai. Only empty wallets \(non-contract wallets with a 0 xDai balance\) receive xDai when bridging. 

Example transaction: [https://blockscout.com/poa/xdai/tx/0xb2620fbd45aa745b3df74058eae9a6fff21242a9ff9645cf55dd2f7a9a47f3c9](https://blockscout.com/poa/xdai/tx/0xb2620fbd45aa745b3df74058eae9a6fff21242a9ff9645cf55dd2f7a9a47f3c9)

Change raw input field from HEX to UTF-8 to view the corresponding note. 

![](../../.gitbook/assets/omni-capture.png)

## BlockScout Faucet

Faucet is now live with SMS phone verification through Twilio\* and multiple hCaptcha prompts to prevent abuse. Virtual numbers are not accepted for faucet transactions.

{% hint style="info" %}
If the faucet is empty there is no time table for a refill. You can use the [OmniBridge faucet ](xdai-faucet.md#blockscout-faucet)when bridging, try the [3rd party faucets](xdai-faucet.md#3rd-party-faucets) below, or [obtain xDai in other ways](../getting-started-with-xdai.md#2-get-a-little-xdai).
{% endhint %}

## Instructions

1\) Go to [https://blockscout.com/xdai/mainnet/faucet](https://blockscout.com/xdai/mainnet/faucet)

1. Enter an `0x...` address where you will receive xDai
2. Enter a valid phone number where you can receive a SMS text message. Be sure to select the correct country with the flag icon.
3. Complete the hCaptcha process.
4. Click **Send SMS.**

![](../../.gitbook/assets/f1.png)

2\) You will be forwarded to the next screen and should receive a text message with a 6 digit code.

1. Enter the 6-digit verification code.
2. Complete the hCaptcha.
3. Click **Request 0.1 xDai**

![](../../.gitbook/assets/f2.png)

You will see a success message. Check your balance on the xDai chain to see that that you received funds from the faucet \(See [getting started with xDai](../getting-started-with-xdai.md) if you have questions around connecting to the xDai chain\).

3\) It is also possible to donate to the faucet and help your community! Click the **Donate button** and complete the transaction in MetaMask to add xDai to the faucet. Donations are automatically set to 10 xDai.

![](../../.gitbook/assets/f3.png)

4\) You are ready to start transacting! You can acquire more xDai directly using a DEX like [HoneySwap](https://honeyswap.org/) without paying high gas fees to bridge Dai from Ethereum.

{% hint style="info" %}
The xDai Faucet can be used by an address once every 24 hours to top-off your xDai balance.
{% endhint %}

## 3rd Party Faucets

A number of additional xDai faucets have been created by projects to assist with xDai onboarding.

* [BAO Community xDai Faucet](https://xdai-app.herokuapp.com/faucet)
* [Minerva Wallet Faucet ](https://minerva.digital/)\(scroll down page to see, must have MIVA to use\)

