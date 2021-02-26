---
description: Using Meta Transaction to enable new Burner Wallet users
---

# Meta Transactions

## Meta transactions for new user onboarding

Meta transactions are an important method for onboarding new users. A user without crypto of any kind \(no Eth, no Dai, no xDai\) can still sign a message and interact with the blockchain without paying transaction fees. These costs are paid instead through an off-chain relayer and relay hub which interacts with a proxy \(recipient\) contract on the user’s behalf.

In the [Burner Wallet \(BW\)](../../for-users/wallets/burner-wallet/) application, a browser-based instant wallet created by [Austin Griffith](https://twitter.com/austingriffith), a user receives a new wallet simply by visiting [xdai.org](https://www.xdai.org). However, this newly created wallet does not contain any funds, so a new user must figure out how to get xDai. If they don’t have a friend to send it to them, this means they need to somehow get Dai, or get Eth and convert it to Dai - then bridge the Dai to xDai. While none of these processes is extremely difficult, they are a lot to ask of someone who has never used crypto.

This is where the link functionality and meta transactions come in.

The link functionality is a process where a current BW user creates a link \(or many links\) which contain an amount of xDai. This link can be sent to anyone, and when the user clicks the link, a new wallet opens up and automatically claims the amount of xDai. Since the new wallet is created with a 0 balance, the transaction costs for claiming funds are paid using meta transactions.

## Meta Transaction Components

Meta transactions can be accomplished in different ways. In this example we use components from [OpenZeppelin's Gas Station Network](https://docs.opengsn.org/). Generally speaking, this process requires a User/Dapp to sign a message, Relayers, a Relay Hub, and a Recipient Contract.

![](../../.gitbook/assets/presentation1.png)

1. The **User/DApp** signs a message which includes function calls, arguments and the users signature. This does not require any gas.
2. The message is sent to an **off-chain relayer**. The relayer creates a signed transaction \(with the user’s signature details\) and sends it to the relay hub.
3. The **relay hub** verifies and funds the transaction and relays it to the the recipient contract. 
4. The **recipient contract** executes the method\(s\) on-chain on behalf of the user.

## How it works with link claims on Burner Wallet

In the case of Burner wallet, there are a few additional calls which are made during the link claiming process.

For context we will create a link to be sent to a new user. **Creating a link does not use meta transactions**.

![Creating a link which contains .55 xDai](../../.gitbook/assets/bw1.gif)

A user can then claim a link. **Claiming a link uses meta transactions**. Here we copy the created link and paste into a browser. A link can be sent in any other way \(email, text etc\). The most common method is to scan a QR code with a mobile device, which creates a new wallet directly on the user's mobile device that scans the code.

![Pasting a claim link into the browser. ](../../.gitbook/assets/bw-2.gif)

## Meta Transaction process for link claiming with Burner Wallet \(BW\)

1. A new BW is created \(or an old one is used if keys exist in local storage\) at [xDai.org](http://xdai.org/)
2. This BW calls the `Links recipient contract` to get the Relay Hub Address
3. BW queries the Relay Hub Contract to get a list of available relayers
4. BW sends a signed tx with hashed call data \(or requests a signature if connected with metamask\) off-chain to the relayers. This does not require gas. 
5. The first off-chain relayer to respond checks that the signed tx is valid.
6. If it is valid, it creates a transaction and sends a `relayCall` message from a funded on-chain EOA \(externally owned account\) to the relay hub.
7. The relay hub sends a `preRelayedCall` to the Links recipient contract
8. Relay hub sends `recipientCallsAtomic` message to itself
9. Relay hub sends `preRelayed` call to Links recipient contract
10. Relay hub sends `claim` call to Links recipient contract
11. Links contract sends a regular tx to the user with claimed funds. User receives the claimed funds into their BW.
12. Relay hub sends final `postRelayedCall` to Links recipient contract.

![](../../.gitbook/assets/meta-transactions-bw.png)

Below is an example claim meta transaction where you can follow the details on encoded messages, logs, internal transactions, and a raw trace of the transaction.

{% embed url="https://blockscout.com/xdai/mainnet/tx/0xaa0ad5d6ed4ce7a5f606b631f0f0a50405db66669327bdd0d4c31db39d3f74e4/internal-transactions" caption="" %}

## Implementation details

In our updated implementation, we use an OpenZeppelin Relayer as well as the OpenZeppelin Relay Hub deployed to the xDai network. The Links recipient contract was created to enable link claiming. A prior implementation using version 0.3 was not functional with the new version of Gas Station Network, so we updated this version to work with GSN v1.

* Links Recipient Contract  [0x5170DA7a3eF514c9F12A3A49EACAF9d026162a1f](https://blockscout.com/xdai/mainnet/address/0x5170DA7a3eF514c9F12A3A49EACAF9d026162a1f/read_contract)
* On-chain Relayer Address \(intermediary between off-chain relayer and relay hub\) [0xc94A34a3f388be34AcaF158FD84331240DAb39a](https://blockscout.com/xdai/mainnet/address/0xc94a34a3f388be34acaf158fd84331240dab39af)
* Relay Hub. This address is the same on all chains where it is deployed. [0xD216153c06E857cD7f72665E0aF1d7D82172F494](https://blockscout.com/xdai/mainnet/address/0xD216153c06E857cD7f72665E0aF1d7D82172F494/read_contract) 
* Pull request where changes were implemented to update contracts to GSNv1: [https://github.com/austintgriffith/burner-wallet/pull/255/files](https://github.com/austintgriffith/burner-wallet/pull/255/files)

_Note: A registration script runs twice daily from the on-chain relayer and calls the `registerRelay` method on the `RelayHub` Contract. This maintains relayer registration on the relay hub.  
Example transaction:_ [_https://blockscout.com/xdai/mainnet/tx/0xf968e16b7c9ffc57622213365601d89067aee04a7615da8674ebc2404a9c810b/internal\_transactions_](https://blockscout.com/xdai/mainnet/tx/0xf968e16b7c9ffc57622213365601d89067aee04a7615da8674ebc2404a9c810b/internal_transactions)\_\_

## Running a GSN Relay Server

In many instances you may want to run your own GSN relayers which interface with the xDai chain. This provides redundancy if a relayer is not functional, expands capacity, and ensures availability if relayers were removed for some reason from the OpenZeppelin implementation.

* David Mihal created a [Docker Image which makes it easy to run on xDai.](https://hub.docker.com/repository/docker/dmihal/gsn-relay-xdai)
* Additional information about launching your own relayer is [available in the GSN docs](https://docs.opengsn.org/tutorials/relay.html#introduction). 

