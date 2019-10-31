---
description: We use a RANDAO-like mechanism to collect and reveal random numbers
---

# RNG Implementation Explainer

{% hint style="info" %}
The POSDAO contracts are available at [https://github.com/poanetwork/posdao-contracts](https://github.com/poanetwork/posdao-contracts).  The following example uses methods from the [RandomAura](https://github.com/poanetwork/posdao-contracts/blob/master/contracts/RandomAuRa.sol) contract.

A [RANDAO ](https://github.com/randao/randao)methodology is used for random number generation.

The following is designed to work with [Parity's AuRa](https://wiki.parity.io/Proof-of-Authority-Chains) consensus protocol, currently in use on the xDai Chain. In this protocol, validators take turns sealing blocks, one after the other, in a prescribed order.
{% endhint %}

### Collection Rounds

POSDAO uses a series of **collection rounds** for random number generation. Each collection round is **38 blocks in length** and split into two equal 19 block phases:

* `commit phase` 
* `reveal phase`

The length of each phase is  `19` blocks \( `38 / 2 = 19`\). When one collection round finishes, the next collection round starts, and so on. For example:

```text
Block number   |   Phase
...
101                Commit phase     <-- collection round #1 started here
102                Commit phase
103                Commit phase
...
117                Commit phase
118                Commit phase
119                Commit phase
120                Reveal phase
121                Reveal phase
122                Reveal phase
...
136                Reveal phase
137                Reveal phase
138                Reveal phase     <-- collection round #1 finished here
139                Commit phase     <-- collection round #2 started here
140                Commit phase
141                Commit phase
...
```

During each collection round, a smart contract collects the random numbers used during that round.

### Commit Phase

1\) Each validator in the set generates a random number \(`secret`\)  locally with their node, hashes the secret, and calls the `commitHash` function when it is their turn to create a block.  

```text
/// @dev Called by the validator's node to store a hash and a cipher of the validator's secret on each collection
/// round. The validator's node must use its mining address (engine_signer) to call this function.
/// This function can only be called once per collection round (during the `commit phase`).
/// @param _secretHash The Keccak-256 hash of the validator's secret.
/// @param _cipher The cipher of the validator's secret. Can be used by the node to restore the lost secret after
/// the node is restarted (see the `getCipher` getter).
function commitHash(bytes32 _secretHash, bytes calldata _cipher) external;
```

2\) This function accepts the hash of the `secret` and its `cipher`. The `cipher` is the `secret` encrypted with a validator's key, and  is needed for the `reveal phase` \(see below\).

For example, if there are three validators, they will call `commitHash` in the following order \(for the sample case above\):

```text
Block number   |   Phase   |       What happens
...
101             Commit phase    Validator1 calls `commitHash`
102             Commit phase    Validator2 calls `commitHash`
103             Commit phase    Validator3 calls `commitHash`
104             Commit phase    Nothing happens
105             Commit phase    Nothing happens
106             Commit phase    Nothing happens
...
117             Commit phase    Nothing happens
118             Commit phase    Nothing happens
119             Commit phase    Nothing happens
120             Reveal phase    Validator1 calls `revealSecret`
121             Reveal phase    Validator2 calls `revealSecret`
122             Reveal phase    Validator3 calls `revealSecret`
123             Reveal phase    Nothing happens
125             Reveal phase    Nothing happens
126             Reveal phase    Nothing happens
...
136             Reveal phase    Nothing happens
137             Reveal phase    Nothing happens
138             Reveal phase    Nothing happens
139             Commit phase    Validator1 calls `commitHash`
140             Commit phase    Validator2 calls `commitHash`
141             Commit phase    Validator3 calls `commitHash`
...
```

When the `commit phase` finishes, the `reveal phase` starts.

### Reveal Phase

When their turn arrives to create a block:

1\) The validator acquires the cipher of the secret using the `getCipher` public getter

```text
/// @dev Returns the cipher of the validator's secret for the specified collection round and the specified validator
/// stored by the validator through the `commitHash` function.
/// @param _collectRound The serial number of the collection round for which the cipher should be retrieved.
/// Should be read with `currentCollectRound()` getter.
/// @param _miningAddress The mining address of validator (engine_signer).
function getCipher(uint256 _collectRound, address _miningAddress) public view returns(bytes memory);
```

2\) The validator decrypts the cipher with their key and retrieves the `secret` 

3\) The validator calls the `revealSecret`function to reveal their committed secret \(and XORs it with the previous secret to create a new random number\)

```text
/// @dev Called by the validator's node to XOR its secret with the current random seed.
/// The validator's node must use its mining address (engine_signer) to call this function.
/// This function can only be called once per collection round (during the `reveal phase`).
/// @param _secret The validator's secret.
function revealSecret(uint256 _secret) external;
```

