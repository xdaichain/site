---
description: Conference wallet walkthrough and features
---

# Pony Purse \(Conference & Event Wallet\)

The Pony Purse is a conference wallet created by the [Splunk](https://www.splunk.com/) Blockchain team. Attendees of the [Splunk conf.19](splunk-conference-non-crypto-conference.md) \(over 10,000 of them!\) used the Pony Purse to purchase items, donate to charity, and interact with games and vendors. The wallet runs on the xDai Chain, leveraging an [Infura endpoint](https://blog.infura.io/infura-brings-scale-to-splunk-xdai-pop-up-cryptocurrency-ab53eda62320) and [Burner Wallet](../../../for-users/wallets/burner-wallet.md) scaffolding to create a seamless user experience. 

Here is a quick walkthrough of the Pony Purse, which uses Buttercup Bucks \(BCB - an ERC20 token created on the xDai chain\) as its cryptocurrency for transactions. User interaction is facilitated through QR codes.

{% hint style="info" %}
At the conference, attendees were onboarded via the conference registration app. This ensured only attendees would get BCB, wallet addresses were known, and key pairs could be recovered easily for each registrant. The example below uses a public url, and keys can be lost easily by logging out of the wallet or using privacy features and closing the browser!
{% endhint %}

## Creating a Wallet

1\) Visit  [pony.cash](https://pony.cash) to create a new wallet.  A web browser on any device will work, but the wallet and experience is optimized for mobile. 

![Click Generate new Pony Purse to start.](../../../.gitbook/assets/bb1.png)

2\) A new wallet will generate with an initial balance of 0.00 Buttercup Bucks.

{% hint style="info" %}
If you previously created a wallet, the same wallet should repopulate when you visit pony.cash \(as long as you are not in stealth mode or cleared your local storage\). Keys are kept in local storage, which allows for easy installation & interaction, but less security.
{% endhint %}

![A fresh Pony Purse, with no transactions.](../../../.gitbook/assets/bcb2.png)

3\) Wallets can be populated by scanning a QR code.  A one-time use code may contain an amount of Buttercup Bucks \(BCBs\), a small amount of xDai to pay for transactions, or Non-Fungible Tokens \(badges\) earned for participating in activities. 

A\) Scan a QR code by pressing the **scan** button on the application home screen. Depending on the browser or device, you may need to enable the camera setting. Scan the QR Code on the back of the buck and the value will quickly populate in the Pony Purse.

![BCB physical tokens](../../../.gitbook/assets/bcb1.png)

4\)  ButterCup Bucks are received. In the example below, BCBs are received via a transfer from one user to another rather than from a BCB physical token \(sent from address 983a2 -&gt; D20Ea, instructions below\). 

![A wallet address receives 2.50 BCB along with a note from the sender.](../../../.gitbook/assets/bcb-3.png)

## Sending and Receiving

Sending and Receiving requires two participants, some BCB to transfer, and a small amount of xDai to pay for transaction costs. Conference users who scan the initial Starter QR code are provided with enough xDai to complete many transactions, and additional xDai can be airdropped to wallet addresses if needed.

{% hint style="info" %}
Since this is an out-of-conference wallet, you may need to transfer a small amount of xDai to your wallet to complete multiple transactions \(gas balance can be viewed in the Advanced screen in the wallet menu\)
{% endhint %}

1\) The Receiver starts by pressing the **Receive** button. This displays the QR code of their wallet.

![Receivers Wallet](../../../.gitbook/assets/bcb4.png)

2\) The Sender then clicks the **Scan** button on their wallet, and scans the Receiver's QR code. 

![Scanning the receiver&apos;s code](../../../.gitbook/assets/scanning-qr-code.png)

3\) Once scanned, the Sender fills in the Amount to send and an optional message to accompany the amount. The Sender clicks **Submit Transaction.**

![Amount and Details entered, click Submit Transaction](../../../.gitbook/assets/send-1.png)

4\) A transaction takes seconds to process.

![Transaction in transit](../../../.gitbook/assets/processing.png)

5\) New Balance and transaction details are reflected in the wallet \(**Senders** wallet shown here\).

![](../../../.gitbook/assets/check_wallet.png)

## Spending

Purchasing items is just as simple. Individual items for sale can be assigned unique QR codes which specify cost \(or is open ended if the user determines the cost\) and other data points. The user simply scans the QR code, information populates about the item, and the transaction is submitted.

### Point of Sale System

Multiple items can also be combined into a single QR code, creating an online shopping cart experience for users. Splunk set up a Point of Sale system using iPad-based terminals which displayed items for sale during the conference. Users could select multiple items/item quantities and add them to their cart. When finished selecting items, the "checkout" button would dynamically generate a single QR code containing details about the order. 

When the user scans the QR code, they see all items and the total cost. The order can then be submitted with a single transaction.

![Multiple items to purchase in a single transaction](../../../.gitbook/assets/pnoy.png)

### Receiving more BCBs

{% hint style="success" %}
In addition to sending BCBs to each other, participants earned BCBs by completed tasks listed on the main page of the app during the event. Users received QR codes for these tasks and scanned them to receive additional BCBs. 
{% endhint %}

## Additional Features

The Burner Wallet ecosystem is rapidly evolving, and new wallets include plugins which enable  xDai purchase using fiat, interactive games, airdrops, and other features. \(See [Burner Wallet Factory](../../../for-developers/burner-wallet-factory/) for up-and-coming plugins\). 

At the Splunk conference, a list of conference-based tasks were available where users could earn NFT tokens \(badges\) and additional BCBs. In addition, some tasks were "hidden", and badges were earned when tasks were unknowingly accomplished by the user \(such as talking to a Splunk executive\). This feature brought interactivity and gamification to the conference.

![NFT badges displayed in the Pony Purse](../../../.gitbook/assets/bscb%20%281%29.png)

## Pony Purse Interface

Since many conference attendees were new to cryptocurrency, the wallet designers kept the menu interface simple and intuitive. 

![Pony Purse features a straightforward user menu](../../../.gitbook/assets/simple-menu.png)

Users looking to learn more about the wallet could visit the **Advanced screen,** which provides details on smart contracts as well as updated xDai block counts, gas \(xDai\) balance, and links to [BlockScout Explorer](https://blockscout.com/poa/xdai/). 

![](../../../.gitbook/assets/advanced-menu.png)

The **Help and About Screen** was also a key component, providing users with needed information and general instructions they could access at any time.

![](../../../.gitbook/assets/help-and-about.png)

{% hint style="success" %}
The Pony Purse was a huge success at conf.19.  It provides a proven, working model for event-based wallets running on the xDai chain.  
{% endhint %}



### 



