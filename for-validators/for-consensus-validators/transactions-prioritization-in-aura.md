# Transactions Prioritization in AuRa

{% hint style="warning" %}
Note: Currently this feature is only supported by the [Nethermind](https://nethermind.io/) client.
{% endhint %}

An xDai/AuRa validator can use the prioritization feature to define transaction inclusion rules. Prioritized transactions are included at the top of a block \(over other, non-prioritized, transactions\) created by the validator.

This can be helpful if a network is spam-attacked or heavily loaded by a project: the prioritization helps ensure necessary transactions are included first \(such as bridge transactions, for example\).

Each validator can set their own prioritization rules that don't depend on the rules of other validators.

There are two independent ways to set prioritization rules:

1. On-chain \(public\): deploy a [TxPriority](https://github.com/poanetwork/posdao-contracts/blob/master/contracts/TxPriority.sol) smart contract and set the rules accordingly as described in [https://github.com/NethermindEth/nethermind/issues/2300](https://github.com/NethermindEth/nethermind/issues/2300).
2. Off-chain \(non-public\): create a local, non-public config file with defined rules.

Both methods can be used independently of each other, or can be used in tandem: in this case, the on-chain and off-chain rules are merged together. The off-chain local rules overlap the on-chain ones if they intersect \(except the whitelist of top priority senders, see below for details\).

### 1. Defining priority rules using a smart contract

To define the rules \(destinations and their weights\), a validator first needs to deploy the [TxPriority contract](https://github.com/poanetwork/posdao-contracts/blob/master/contracts/TxPriority.sol). The constructor accepts the address of the contract's owner. Only the contract's owner can manage it.

After the contract is deployed, its address needs to be defined in the `Aura/TxPriorityContractAddress` config option in the node's config. Example config: [https://github.com/poanetwork/posdao-test-setup/blob/86d6a3d057a6c1326517a0c58486c2047e130a7b/config/node1.nethermind.json\#L39](https://github.com/poanetwork/posdao-test-setup/blob/86d6a3d057a6c1326517a0c58486c2047e130a7b/config/node1.nethermind.json#L39)

{% hint style="info" %}
After completing the config file modifications, the node must be restarted.
{% endhint %}

#### 1.1 Destinations and weights

The prioritization rule is a transaction destination and its weight. It consists of the following fields:

* tx target address \(target\)
* function's signature \(fnSignature\)
* priority \(weight\)

The `TX target address` is the `to` field of the transaction. It defines the address the transaction is sent to and can be either a contract or EOA. It cannot be zero address `0x00...00`.

The `function's signature` is the first 4 bytes of a transaction's `data` field. It is set as an actual vaue when the `target` is a contract address and we want to prioritize one of its functions. For example, if we want to prioritize the `transfer(address,uint256)` function of some ERC20 contract, the `fnSignature` for that will be `0xa9059cbb` \(see [How to get Ethereum encoded function signatures](https://medium.com/@piyopiyo/how-to-get-ethereum-encoded-function-signatures-1449e171c840)\).

The `fnSignature` can be empty \(`0x00000000`\) if we want to prioritize a transaction which sends native coins to a `target` address \(regardless of whether it's a contract, or not\), i.e. when TX's `data` is empty.

The `target + fnSignature` is a `destination`.

The `weight` defines the destination's priority: a destination with a higher weight will have a higher priority than another destination with a lower weight. The weight for each destination is unique and cannot be zero.

For example, we defined the following two rules:

```text
target = 0xaa...bb
fnSignature = 0x12345678
weight = 2000

target = 0xaa...bb
fnSignature = 0x90876543
weight = 1000
```

In this case, if there are transactions in the TX pool with such destinations, the transactions matching the first destination \(with weight = 2000\) will be mined earlier than transactions matching the second one \(with weight = 1000\). If there is a transaction with the same `to` field but with a different signature in the `data` \(the first 4 bytes\), it won't be prioritized because there are no rules \(destinations\) defined for it.

If we define the following rule

```text
target = 0xcc...dd
fnSignature = 0x00000000
weight = 3000
```

it will only apply to transactions with the empty `data` field and the `to` field equal to `0xcc...dd`.

To manage on-chain priority rules, there are three functions in the `TxPriority` contract:

1. [setPriority](https://github.com/poanetwork/posdao-contracts/blob/dd38a16d9e049295f4eca6ae74927530a082b22f/contracts/TxPriority.sol#L61-L69) define/modify a destination with its unique weight.
2. [removePriority](https://github.com/poanetwork/posdao-contracts/blob/dd38a16d9e049295f4eca6ae74927530a082b22f/contracts/TxPriority.sol#L92-L96) remove a previously defined destination \(make it non-prioritized\).
3. [getPriorities](https://github.com/poanetwork/posdao-contracts/blob/dd38a16d9e049295f4eca6ae74927530a082b22f/contracts/TxPriority.sol#L171-L173) public getter to view all existing on-chain priority rules sorted by weight descending.

For convenience, a validator can verify their `TxPriority` contract in [Blockscout explorer](https://blockscout.com/) and use the `Read Contract` and `Write Contract` tabs in Blockscout's UI to call the functions.

#### 1.2 Whitelist of top priority senders

There can be a short whitelist of `from` addresses which receive top priority \(higher than others defined by the `setPriority` contract function\).

If there is a transaction with the `from` field matching one of the whitelisted addresses, such a transaction will be prioritized higher than others, including those set by the `setPriority` function.

There are two functions for managing the whitelist in the `TxPriority` contract:

1. [setSendersWhitelist](https://github.com/poanetwork/posdao-contracts/blob/dd38a16d9e049295f4eca6ae74927530a082b22f/contracts/TxPriority.sol#L109-L113).
2. [getSendersWhitelist](https://github.com/poanetwork/posdao-contracts/blob/dd38a16d9e049295f4eca6ae74927530a082b22f/contracts/TxPriority.sol#L185-L186) public getter.

#### 1.3 Additional Min Gas Price filtering

In some cases, a validator may want to increase the Min Gas Price required to mine specified transactions. This is not for prioritization, but for tx filtering: if a transaction has a `gasPrice` lower than the required Min Gas Price, it will not be mined by the validator.

There following functions in `TxPriority` contract are used to manage Min Gas Prices:

1. [setMinGasPrice](https://github.com/poanetwork/posdao-contracts/blob/dd38a16d9e049295f4eca6ae74927530a082b22f/contracts/TxPriority.sol#L118-L129). Note that the `minGasPrice` cannot be zero and will be ignored by validator's node if it is less than the [MinGasPrice](https://github.com/poanetwork/posdao-test-setup/blob/86d6a3d057a6c1326517a0c58486c2047e130a7b/config/node1.nethermind.json#L51) global option defined in node's config.
2. [removeMinGasPrice](https://github.com/poanetwork/posdao-contracts/blob/dd38a16d9e049295f4eca6ae74927530a082b22f/contracts/TxPriority.sol#L149-L152).
3. [getMinGasPrices](https://github.com/poanetwork/posdao-contracts/blob/dd38a16d9e049295f4eca6ae74927530a082b22f/contracts/TxPriority.sol#L190-L191) public getter.

Please, see `setMinGasPrice` description for details: [https://github.com/poanetwork/posdao-contracts/blob/dd38a16d9e049295f4eca6ae74927530a082b22f/contracts/TxPriority.sol\#L118-L128](https://github.com/poanetwork/posdao-contracts/blob/dd38a16d9e049295f4eca6ae74927530a082b22f/contracts/TxPriority.sol#L118-L128)

If you skipped the [Destinations and weights](transactions-prioritization-in-aura.md#1-1-destinations-and-weights) section above, please read it first to get what `target` and `fnSignature` fields are.

### 2. Defining priority rules locally \(off-chain\)

Everything described above in [Defining priority rules with the smart contract](transactions-prioritization-in-aura.md#2-defining-priority-rules-locally-off-chain) can be set through a local config file. If you didn't read the section above, please read it first to understand the basic principles.

To define the config path in your filesystem, use the `Aura/TxPriorityConfigFilePath` option in node's config. Example: [https://github.com/poanetwork/posdao-test-setup/blob/86d6a3d057a6c1326517a0c58486c2047e130a7b/config/node1.nethermind.json\#L40](https://github.com/poanetwork/posdao-test-setup/blob/86d6a3d057a6c1326517a0c58486c2047e130a7b/config/node1.nethermind.json#L40) 

{% hint style="info" %}
Note: it is better to use an absolute path to the file.
{% endhint %}

The TxPriority config file should be JSON formatted. 

Example of the file with different rules:

```text
{
  "whitelist": [
    "0x475674cb523a0a2736b7f7534390288fce16982c",
    "0x692921b14f1b1c385cd7e0cc2ef7abe5598c1234"
  ],
  "priorities": [
    {
      "target": "0x113321b14f1b1c385cd7e0cc2ef7abe5598c4321",
      "fnSignature": "0x00010203",
      "value": "300"
    },
    {
      "target": "0x76e68a8696537e4141926f3e528733af9e237d69",
      "fnSignature": "0x00010203",
      "value": "200"
    },
    {
      "target": "0x942921b14f1b1c385cd7e0cc2ef7abe5598c8358",
      "fnSignature": "0x00000000",
      "value": "100"
    }
  ],
  "minGasPrices": [
    {
      "target": "0x762921b14f1b1c385cd7e0cc2ef7abe5598c8459",
      "fnSignature": "0x00010203",
      "value": "5000000000"
    },
    {
      "target": "0x83e68a8696537e4141926f3e528733af9e237e78",
      "fnSignature": "0x00010203",
      "value": "3000000000"
    },
    {
      "target": "0x552921b14f1b1c385cd7e0cc2ef7abe5598c8473",
      "fnSignature": "0x00000000",
      "value": "2000000000"
    }
  ]
}
```

The file with empty rules looks like this:

```text
{
  "whitelist": [],
  "priorities": [],
  "minGasPrices": []
}
```

{% hint style="warning" %}
The changes in the TxPriority config file take effect immediately without having to restart the node.
{% endhint %}

### 3. Combining both methods

As mentioned above, both methods \(on-chain and off-chain\) can be used independently of each other, or they can be used at the same time.

When combining on-chain and off-chain rules, they will be merged together. The off-chain local rules overrule the on-chain ones if they intersect. For example:

We made the following call:

`setPriority(0x443321b14f1b1c385cd7e0cc2ef7abe5598c0000, 0x12345678, 1000)`

and we set a local \(off-chain\) rule for the same destination but with a different weight:

```text
{
  "whitelist": [],
  "priorities": [
    {
      "target": "0x443321b14f1b1c385cd7e0cc2ef7abe5598c0000",
      "fnSignature": "0x12345678",
      "value": "2000"
    }
  ],
  "minGasPrices": []
}
```

The weight for the destination `target = 0x443321b14f1b1c385cd7e0cc2ef7abe5598c0000, fnSignature = 0x12345678` will have the weight of `2000` because the local \(off-chain\) rule takes precedence over the rule from the TxPriority contract.

The same goes for `minGasPrices` rules.

#### 3.1 Whitelist Rules

Note that `whitelist` rules differ - these rules are combined from both on-chain and off-chain methods.

For example we make the following call:

`setSendersWhitelist([0x226621b14f1b1c385cd7e0cc2ef7abe5598c5555])`

and we whitelisted another address in the local file:

```text
{
  "whitelist": ["0x885521b14f1b1c385cd7e0cc2ef7abe5598c7777"],
  "priorities": [],
  "minGasPrices": []
}
```

As a result, both addresses are whitelisted:

* 0x226621b14f1b1c385cd7e0cc2ef7abe5598c5555
* 0x885521b14f1b1c385cd7e0cc2ef7abe5598c7777

### 4. Nuances of the prioritization

4.1. If an address sends two transactions with the same `gasPrice` and `nonce`, the transaction with the higher weight will be picked up \(if its destination is prioritized\).

4.2. If an address sends two transactions with different nonces, the transaction with a lower nonce will be picked up earlier than the second transaction with a higher nonce regardless of whether the transactions are prioritized or not.

4.3. If an address sends two transactions with the same nonce, but with different gasPrices, the transaction with a higher gas price will be picked up earlier than the second transaction having a lower gas price regardless of whether the transactions are prioritized or not.

4.4. If there are two non-prioritized transactions in the TX pool, they will be picked up according to their gas prices \(a higher gas price has a higher priority\).

4.5. If whitelisted addresses send multiple transactions, the transactions will be ordered according to their weights \(if set\).

