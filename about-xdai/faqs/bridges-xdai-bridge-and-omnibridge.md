# Bridges: xDai Bridge & OmniBridge

{% hint style="info" %}
The TokenBridge project is responsible for the xDai Bridge, OmniBridge and many other bridges in development for cross-chain interaction. For additional details, see the bridge documentation at [docs.tokenbridge.ne](https://docs.tokenbridge.net/)
{% endhint %}

## Why are there Multiple Bridges?

Different bridges exist to support different operations. Two bridges currently exist on the xDai chain. Additional bridges and/or extensions may be deployed in the future.

* **xDai Bridge**: Convert Dai to xDai and xDai to Dai
* **OmniBridge**: Convert ERC20 tokens on Mainnet to equivalent ERC677 tokens on the xDai chain

The [Optimistic Omnibridge](https://ethresear.ch/t/optimistic-bridge-between-mainnet-and-a-pos-chain/7965) is also in development to provide a bridge for trustless transfers from xDai to Ethereum.

## xDai Bridge FAQs

### Why is the xDai Bridge important?

The bridge is a key element of xDai which allows for interoperability between xDai and the mainnet. The bridge connects the networks and allows tokens to exist on both sides. To mint xDai, Dai is locked in the bridge contract and the equivalent amount of xDai is created on the xDai chain. In order to return this xDai to Dai, xDai is burned and Dai is unlocked.

### What are the transfer limits when using the xDai Bridge?

The current limits are below. Note that these can be changed by a majority vote from the Governance Board.

|  |  |  |
| :--- | :--- | :--- |
| Max Single Deposit | 9,999,999 Dai | 9,999,999 xDai |
| Minimum Transfer | 0.005 Dai | 10 xDai |
| Transaction \(Gas\) Fees | variable, paid in Eth | paid in xDai |
| Transfer Fees \(in addition to gas fees\) | 0%  | 0% |

### What is the Bridge Governance Board?

The Governance Board is responsible for managing bridge operations on both sides of the bridge \(contracts are deployed on the Ethereum and xDai side\). Management operations may include:

* Bridge contract updates
* Bridge validator updates \(changing validator set\)
* Contract parameters like limits, finality threshold, gas price fallback etc.
* Bridge validator parameters like changing the validators set or signatures threshold.

All these actions will be managed through Gnosis Safe accounts, one on the Ethereum mainnet for Ethereum contract side operations and one on xDai for xDai contract operations. Currently 6/11 signatures are required to enact a proposal.

* [Current xDai Bridge Governance Board Members](../../for-validators/for-bridge-validators/)
* Gnosis Safe contract on Ethereum: [https://gnosis-safe.io/app/\#/safes/0x42F38ec5A75acCEc50054671233dfAC9C0E7A3F6/settings](https://gnosis-safe.io/app/#/safes/0x42F38ec5A75acCEc50054671233dfAC9C0E7A3F6/settings)
* Gnosis Safe contract on xDai: [https://xdai.gnosis-safe.io/app/\#/safes/0x7a48Dac683DA91e4faa5aB13D91AB5fd170875bd/settings](https://xdai.gnosis-safe.io/app/#/safes/0x7a48Dac683DA91e4faa5aB13D91AB5fd170875bd/settings)

{% hint style="info" %}
For more on this transition, see the forum proposal: [https://forum.poa.network/t/increase-number-of-participants-in-the-xdai-bridge-management-multsigs/3773](https://forum.poa.network/t/increase-number-of-participants-in-the-xdai-bridge-management-multsigs/3773)
{% endhint %}

### Who are the validators of the xDai Bridge?

There are currently [4 bridge validators](../../for-validators/for-bridge-validators/), and 3/4 signatures are required for bridge transactions. The validator set can be updated by the Governance Board.

### I completed a transfer of Dai to xDai and see the transaction to lock Dai, but do not see the transaction that "mints" xDai. How does it work?

1. Oracles send confirmations of the transaction to the bridge contract. 
2. After receiving the required number of confirmations, the bridge contract sends a request to the Block Reward contract to schedule emission of new xDai \(the same amount as requested in the bridge tx\).
3. The Block Reward contract is invoked by the xDai network validator during the last step of block verification, and  account balances are updated in the Block Reward contract. 

{% hint style="info" %}
Example transaction executing a transfer: [https://blockscout.com/poa/xdai/tx/0x799abac45b6c2ab18728b3baa04d112f8af8fba4d34d8078cf93856c71e73b91/internal-transactions](https://blockscout.com/poa/xdai/tx/0x799abac45b6c2ab18728b3baa04d112f8af8fba4d34d8078cf93856c71e73b91/internal-transactions)
{% endhint %}

{% hint style="info" %}
Transactions can be investigated in further detail using [Tenderly](https://tenderly.co/).
{% endhint %}

## OmniBridge FAQs

_Coming soon_





