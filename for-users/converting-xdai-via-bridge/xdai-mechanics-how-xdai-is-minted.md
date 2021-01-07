# xDai mechanics: How xDai is minted

The xDai token is minted when Dai is transferred from Ethereum to the xDai Chain using the xDai Bridge. During the transfer process, a block reward contract is invoked to mint xDai to a user's account. Because contract calls are made from the consensus engine to create xDai tokens, balance updates are more difficult to trace than simple value transfers. 

### **Basic Process**

1. A user sends a transaction to the [bridge contract](https://etherscan.io/address/0x4aa42145Aa6Ebf72e164C9bBC74fbD3788045016#code) on Ethereum to initiate a transfer.
2. The transfer is approved on the Ethereum side and the user's Dai balance is reduced accordingly.
3. Bridge validator oracles invoke the `executeAffirmation` method to confirm the transfer request.
4. When enough confirmations are collected \(a majority of oracles must confirm\), the [bridge contract](https://blockscout.com/poa/xdai/address/0x7301CFA0e1756B71869E93d4e4Dca5c7d0eb0AA6/transactions) on xDai calls the xDai [block reward contract](https://blockscout.com/poa/xdai/address/0x481c034c6d9441db23Ea48De68BCAe812C5d39bA).
5. The block reward contract records the receiver\(s\) and amount\(s\) of xDai to mint. There may be more than 1 bridge transaction per block.
6. The block reward contract is called by the AuRa consensus engine to update the EVM state and update the user's xDai balance.

### **View a Transaction**

You can view a receiver's address and amount of xDai received in the block reward contract logs. Whenever the `executeAffirmation` method is called, it registers the following:  
 `AddedReceiver(uint256 amount, address indexed receiver, address indexed bridge)`

**Example:**   
[https://blockscout.com/poa/xdai/tx/0x5892a695860f6087a2d93140f05e6365142ff77fd7128e39dbc03128d5797ac4/logs.](https://blockscout.com/poa/xdai/tx/0x5892a695860f6087a2d93140f05e6365142ff77fd7128e39dbc03128d5797ac4/logs.)

### More Information

* To view xDai minting transactions from an account that received xDai, you can [find the block and subsequent transaction using the coin history tab in BlockScout](viewing-inbound-transactions.md). 
* More information on the [OpenEthereum Block Reward contract is available here](https://openethereum.wiki/Block-Reward-Contract).







