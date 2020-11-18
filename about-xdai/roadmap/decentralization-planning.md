# Decentralization Planning

As xDai adoption continues at a rapid clip, we are working behind the scenes to create more decentralized operations for users of the xDai chain. Public POSDAO will introduce greater chain decentralization through validation and delegation assignments based on the amount of STAKE locked in the protocol rather than permissioned validators. This transition is scheduled to take effect in Q1 2021.

Bridge decentralization is also needed, and we are making progress on multiple fronts.

### 1\) Decentralized Bridge Withdrawals

* Target Date: October 8, 2020
* [More Information](https://forum.poa.network/t/important-changes-in-a-user-interaction-with-the-xdai-bridge/3906)

Rather than depending on oracles to transfer withdrawal requests, users will control their own withdrawal process and submit transactions directly. This will provide increased transparency and fee management abilities for users when bridging assets from xDai to Ethereum.

### 2\) Increase Bridge Governance Set on xDai Bridge

* Target Dates:
  * Bridge Contract on Ethereum Side: **Completed**
  * Bridge Contract on xDai Side: **Completed**
* [More Information](https://forum.poa.network/t/increase-number-of-participants-in-the-xdai-bridge-management-multsigs/3773)

Historically, validators on the xDai Bridge have been entrusted with validating transaction as well as making all governance decisions related to bridge operations. While the current validators will remain \(POA Network, MakerDAO, Giveth and Protofire\), the governor set tasked with making all decisions regarding bridge operations will be expanded. 

To enable this transition, a Gnosis Safe will be used to manage governors. Eleven governors will make up the initial set, and they will have the ability to upgrade bridge contracts, extend the bridge validators set, and update bridge parameters such as block confirmations, tx limits and fees. 6 of 11 signatures will be required to approve operations.

Future plans include upgrading the AMB \(OmniBridge\) governance structure as well.

### 3\) Optimistic OmniBridge

* Target Date: Q4 2020
* [More Information](https://ethresear.ch/t/optimistic-bridge-between-mainnet-and-a-pos-chain/7965)

A new bridge type will be architected where users can withdraw assets from xDai and claim them on Ethereum completely independently, with xDai POS chain validators act as claim challengers. This design gives users more control of cross-chain funds movement.   
  
The Optimistic Omnibridge \(OO\) will likely be deployed in addition to current bridges, providing users with a choice as to which bridge they would like to use. OO will be slower and require a refundable bond in Ether, but will provide additional security and control for users.





