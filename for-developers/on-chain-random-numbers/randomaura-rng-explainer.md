# RandomAura RNG Explainer

{% hint style="success" %}
The following example uses methods from the [RandomAura](https://github.com/poanetwork/posdao-contracts/blob/master/contracts/RandomAuRa.sol) contract. A [RANDAO ](https://github.com/randao/randao)methodology implemented by the validator nodes generates pseudorandom numbers.

The following is designed to work with [Parity's AuRa](https://wiki.parity.io/Proof-of-Authority-Chains) consensus protocol v2.7.2+. In this protocol, validators take turns sealing blocks, one after the other, in a prescribed order.
{% endhint %}

### Collection Rounds

A series of **collection rounds** are used for random number generation. The  collection round length is configurable - in this example we use 38 blocks for a round, ****split into two equal 19 block phases:

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

During each collection round, the RandomAura contract \(see below\) collects the random numbers generated during that round.

### Commit Phase

1\) Each validator in the set generates a random `number` locally with their node, hashes the secret, and calls the `commitHash` function when it is their turn to create a block.  

```javascript
/// @dev Called by the validator's node to store a hash and a cipher of the validator's number on each collection
/// round. The validator's node must use its mining address (engine_signer) to call this function.
/// This function can only be called once per collection round (during the `commit phase`).
/// @param _numberHash The Keccak-256 hash of the validator's number.
/// @param _cipher The cipher of the validator's number. Can be used by the node to restore the lost number after
/// the node is restarted (see the `getCipher` getter).
function commitHash(bytes32 _numberHash, bytes calldata _cipher) external {
    address miningAddress = msg.sender;

    require(block.coinbase == miningAddress);
    require(isCommitPhase()); // must only be called in `commit phase`
    require(_numberHash != bytes32(0));
    require(!isCommitted(currentCollectRound(), miningAddress)); // cannot commit more than once

    uint256 collectRound = currentCollectRound();

    _commits[collectRound][miningAddress] = _numberHash;
    _ciphers[collectRound][miningAddress] = _cipher;
}
```

2\) This function accepts the hash of the secret `number` and its `cipher`. The `cipher` is the `number` encrypted with a validator's key, and  is needed for the `reveal phase` \(see below\).

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

When a validator's turn arrives to create a block:

1\) The validator gets the cipher of the number using the `getCommitAndCipher` public getter.

```javascript
/// @dev Returns the Keccak-256 hash and cipher of the validator's number for the specified collection round
/// and the specified validator stored by the validator through the `commitHash` function.
/// @param _collectRound The serial number of the collection round for which hash and cipher should be retrieved.
/// @param _miningAddress The mining address of validator (engine_signer).
function getCommitAndCipher(
    uint256 _collectRound,
    address _miningAddress
) public view returns(bytes32, bytes memory) {
    return (_commits[_collectRound][_miningAddress], _ciphers[_collectRound][_miningAddress]);
}
```

2\) The validator decrypts the cipher with their key and retrieves the `number`.

3\) The validator calls the `revealNumber`function to reveal their committed number \(the function XORs the number with the previous seed to create a new random seed stored in the `currentSeed` state variable\).

```javascript
/// @dev Called by the validator's node to XOR its number with the current random seed.
/// The validator's node must use its mining address (engine_signer) to call this function.
/// This function can only be called once per collection round (during the `reveal phase`).
/// @param _number The validator's number.
function revealNumber(uint256 _number) external {
    address miningAddress = msg.sender;

    bytes32 numberHash = keccak256(abi.encodePacked(_number));
    uint256 collectRound = currentCollectRound();

    require(block.coinbase == miningAddress);
    require(!isCommitPhase()); // must only be called in `reveal phase`
    require(numberHash != bytes32(0));
    require(numberHash == _commits[collectRound][miningAddress]); // the hash must be commited
    require(!_sentReveal[collectRound][miningAddress]); // cannot reveal more than once during the same collect round

    currentSeed = currentSeed ^ _number;

    _sentReveal[collectRound][miningAddress] = true;
    delete _commits[collectRound][miningAddress];
    delete _ciphers[collectRound][miningAddress];
}
```

{% hint style="info" %}
_Note: Randomness created in a deterministic manner, through computerized means, it is called pseudorandomness. Pseudorandom numbers exhibit the same properties as random numbers. The method described above is technically a pseudorandom number generator \(PRNG\)_
{% endhint %}

## RandomAura Contract Code

The RandomAura Contract interfaces with the Authority Round consensus process to store and iterate the `currentSeed` , control when the seed is revealed, and report on skipped reveals by Validators.

Below is the full RandomAura contract code \(its POSDAO implementation is located at [https://github.com/poanetwork/posdao-contracts/blob/master/contracts/RandomAuRa.sol](https://github.com/poanetwork/posdao-contracts/blob/master/contracts/RandomAuRa.sol)

```javascript
pragma solidity 0.5.16;


/// @dev Generates and stores random numbers in a RANDAO manner (and controls when they are revealed by AuRa
/// validators) and accumulates a random seed.
contract RandomAuRa {

    mapping(uint256 => mapping(address => bytes)) internal _ciphers;
    mapping(uint256 => mapping(address => bytes32)) internal _commits;
    mapping(uint256 => mapping(address => bool)) internal _sentReveal;

    /// @dev The length of the collection round (in blocks).
    uint256 public constant collectRoundLength = 38;

    /// @dev The current random seed accumulated.
    uint256 public currentSeed;

    /// @dev Called by the validator's node to store a hash and a cipher of the validator's number on each collection
    /// round. The validator's node must use its mining address (engine_signer) to call this function.
    /// This function can only be called once per collection round (during the `commit phase`).
    /// @param _numberHash The Keccak-256 hash of the validator's number.
    /// @param _cipher The cipher of the validator's number. Can be used by the node to restore the lost number after
    /// the node is restarted (see the `getCipher` getter).
    function commitHash(bytes32 _numberHash, bytes calldata _cipher) external {
        address miningAddress = msg.sender;

        require(block.coinbase == miningAddress);
        require(isCommitPhase()); // must only be called in `commit phase`
        require(_numberHash != bytes32(0));
        require(!isCommitted(currentCollectRound(), miningAddress)); // cannot commit more than once

        uint256 collectRound = currentCollectRound();

        _commits[collectRound][miningAddress] = _numberHash;
        _ciphers[collectRound][miningAddress] = _cipher;
    }

    /// @dev Called by the validator's node to XOR its number with the current random seed.
    /// The validator's node must use its mining address (engine_signer) to call this function.
    /// This function can only be called once per collection round (during the `reveal phase`).
    /// @param _number The validator's number.
    function revealNumber(uint256 _number) external {
        address miningAddress = msg.sender;

        bytes32 numberHash = keccak256(abi.encodePacked(_number));
        uint256 collectRound = currentCollectRound();

        require(block.coinbase == miningAddress);
        require(!isCommitPhase()); // must only be called in `reveal phase`
        require(numberHash != bytes32(0));
        require(numberHash == _commits[collectRound][miningAddress]); // the hash must be commited
        require(!_sentReveal[collectRound][miningAddress]); // cannot reveal more than once during the same collect round

        currentSeed = currentSeed ^ _number;

        _sentReveal[collectRound][miningAddress] = true;
        delete _commits[collectRound][miningAddress];
        delete _ciphers[collectRound][miningAddress];
    }

    /// @dev Returns the serial number of the current collection round.
    /// Needed when using `getCommit`, `isCommitted`, `sentReveal`, or `getCipher` getters (see below).
    function currentCollectRound() public view returns(uint256) {
        return (block.number - 1) / collectRoundLength;
    }

    /// @dev Returns the Keccak-256 hash and cipher of the validator's number for the specified collection round
    /// and the specified validator stored by the validator through the `commitHash` function.
    /// @param _collectRound The serial number of the collection round for which hash and cipher should be retrieved.
    /// @param _miningAddress The mining address of validator (engine_signer).
    function getCommitAndCipher(
        uint256 _collectRound,
        address _miningAddress
    ) public view returns(bytes32, bytes memory) {
        return (_commits[_collectRound][_miningAddress], _ciphers[_collectRound][_miningAddress]);
    }

    /// @dev Returns a boolean flag indicating whether the specified validator has committed their number's hash for the
    /// specified collection round.
    /// @param _collectRound The serial number of the collection round for which the checkup should be done.
    /// Should be read with `currentCollectRound()` getter.
    /// @param _miningAddress The mining address of the validator (engine_signer).
    function isCommitted(uint256 _collectRound, address _miningAddress) public view returns(bool) {
        return _commits[_collectRound][_miningAddress] != bytes32(0);
    }

    /// @dev Returns a boolean flag of whether the specified validator has revealed their number for the
    /// specified collection round.
    /// @param _collectRound The serial number of the collection round for which the checkup should be done.
    /// Should be read with `currentCollectRound()` getter.
    /// @param _miningAddress The mining address of the validator (engine_signer).
    function sentReveal(uint256 _collectRound, address _miningAddress) public view returns(bool) {
        return _sentReveal[_collectRound][_miningAddress];
    }

    /// @dev Returns a boolean flag indicating whether the current phase of the current collection round
    /// is a `commit phase`. Used by the validator's node to determine if it should commit the hash of
    /// the number during the current collection round.
    function isCommitPhase() public view returns(bool) {
        uint256 commitPhaseLength = collectRoundLength / 2;
        return ((block.number - 1) % collectRoundLength) < commitPhaseLength;
    }
    
    /// @dev Returns the number of the first block of the current collection round.
    function currentCollectRoundStartBlock() public view returns(uint256) {
        return currentCollectRound() * collectRoundLength + 1;
    }

    /// @dev Returns the number of the first block of the next (future) collection round.
    function nextCollectRoundStartBlock() public view returns(uint256) {
        uint256 remainingBlocksToNextRound = collectRoundLength - (block.number - 1) % collectRoundLength;
        return block.number + remainingBlocksToNextRound;
    }

    /// @dev Returns the number of the first block of the next (future) commit phase.
    function nextCommitPhaseStartBlock() public view returns(uint256) {
        return nextCollectRoundStartBlock();
    }

    /// @dev Returns the number of the first block of the next (future) reveal phase.
    function nextRevealPhaseStartBlock() public view returns(uint256) {
        uint256 commitPhaseLength = collectRoundLength / 2;
        if (isCommitPhase()) {
            return currentCollectRoundStartBlock() + commitPhaseLength;
        } else {
            return nextCollectRoundStartBlock() + commitPhaseLength;
        }
    }

}

```

