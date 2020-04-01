---
description: On-chain randomness questions and answers
---

# Randomness FAQs

## Is on-chain randomness available now? <a id="is-on-chain-randomness-available-now"></a>

**Yes!** it is activated on the xDai Chain. The RandomAura contract provides on-chain random numbers.

| Name | Address |
| :--- | :--- |
| RandomAuRaCode | 0x77bfEd71b26998Bb9eBd9864e3eC169A5C91504C |
| RandomAuRaProxy | 0x5870b0527DeDB1cFBD9534343Feda1a41Ce47766 |

## How is randomness created on-chain? <a id="how-is-randomness-created-on-chain"></a>

Currently, randomness is created through a [RANDAO](https://github.com/randao/randao)-like process, where validators commit the hash of a random number to the chain, then reveal that number later on. The revealed number is XORd with a previous random seed, creating a new random seed. For more details, see [https://forum.poa.network/t/reliable-randomness-bringing-on-chain-entropy-to-the-xdai-stable-chain/3015](https://forum.poa.network/t/reliable-randomness-bringing-on-chain-entropy-to-the-xdai-stable-chain/3015)​

In the future, we will have [secure, per-block randomness when HoneyBadger BFT is introduced.](https://www.poa.network/for-developers/on-chain-random-numbers/randomness-faqs#will-on-chain-unpredictable-random-numbers-per-block-be-available-in-the-future)​

## Is an unpredictable random value created on every block? <a id="is-an-unpredictable-random-value-created-on-every-block"></a>

**No!** Random values are only created during the **reveals phase**, which occurs on Sokol every 20 blocks and continues for a period of 20 blocks \(note this value is configurable\).

A complete collection phase on Sokol is currently set to 40 blocks. The first half \(the first 20 blocks\) is called the commit phase, where random number hashes are committed by validators. The second half \(the second 20 blocks\) is the reveal phase, where numbers are revealed and added to the `currentSeed` getter.

Entropy increases throughout the reveal phase, and the final number revealed is the most secure. Applications requiring secure randomness should retrieve the `currentSeed` from the final block of a reveal phase or during a commit phase.

## How do I access a random value from my smart contract? <a id="how-do-i-access-a-random-value-from-my-smart-contract"></a>

The value is contained in the `currentSeed` getter. It is important to check the phase \(`commit` or `reveal`\) and determine when the value is created. Details are available on the [Accessing a Random Seed with a Smart Contract](https://www.poa.network/for-developers/on-chain-random-numbers/accessing-a-random-seed-with-a-smart-contract) page.

Business logic actions that require randomness should not be allowed during the reveal phase. In addition, **randomness can never be guaranteed for block** **`N + 1`**, only for some block between `N + commitRoundLength` and `N + 2*commitRoundLength`.

## How do I generate multiple random numbers from a single block? <a id="how-do-i-generate-multiple-random-numbers-from-a-single-block"></a>

It is possible to create an on-chain PRNG where the `currentSeed` value is used to seed a generator. However, as soon as the seed is known, the whole sequence is known! To add additional entropy, the seed may be salted with the block hash, however this method is still not considered secure.

 A simple way to turn a single seed into multiple numbers is to use `hash(currentseed+0)` , `hash(currentseed+1)`, `hash(currentseed+2)`, etc., or something similar \(e.g. `hash(currentseed+previousHash)`\). Limitations of this method \(regarding security and speed\) are discussed here: [https://stackoverflow.com/questions/14467805/can-a-cryptographic-hash-algorithm-be-used-as-a-prng](https://stackoverflow.com/questions/14467805/can-a-cryptographic-hash-algorithm-be-used-as-a-prng)​

## How secure is this method of on-chain random number generation? <a id="how-secure-is-this-method-of-on-chain-random-number-generation"></a>

While secure, there are considerations to keep in mind. They have to do with malicious validators who may choose to manipulate the outcome by not revealing their number. Validators cannot change the number they have committed, but they can choose to not commit or not reveal a number.

This means that during the reveal phase, a validator can effectively choose between 2 numbers, either the current number or the new one that will be created when they reveal their number. If an application uses the final number of the reveals phase, only the final validator can make this choice, limiting the scope of this issue.

To discourage skipping, validators who skip too often \(or skip at the end of an epoch\) will be reported as malicious. In POSDAO \(a proof-of-stake algorithm that may be implemented in the future\), malicious validators will be banned from the protocol for 90 days and their STAKE frozen. For now, we will monitor the network for any malicious behavior and validators can determine and vote on consequences.

Since validators on Sokol and POA are known individuals staking their reputation, this is not as much a concern as it would be in a permissionless network.

## Will on-chain, unpredictable random numbers per block be available in the future? <a id="will-on-chain-unpredictable-random-numbers-per-block-be-available-in-the-future"></a>

**YES!** When we move to HoneyBadger BFT, reliable random numbers will be produced per block via threshold signatures.

Using this approach, validators will signal their approval of a block by providing a portion of a signature \(a signature share\) rather than the entire signature. Once a predetermined number of shares are received by the algorithm \(the threshold\), they are combined to create a single signature which cannot be known beforehand. Because this number is secret until it is revealed, it can be used as a random number. A special property of this algorithm is that any combination of validators can collaborate to create the same final signature.

For more on HoneyBadger BFT, see [https://www.xdaichain.com/for-validators/consensus/honeybadger-bft-consensus](https://www.xdaichain.com/for-validators/consensus/honeybadger-bft-consensus)

