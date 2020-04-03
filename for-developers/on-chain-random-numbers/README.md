# On-Chain Random Numbers

The xDai stable chain features an on-chain RNG based on RANDAO. It may be leveraged by smart contract developers to introduce random numbers into their applications.  _Note that random numbers are limited to certain blocks in the current implementation. See below for more information._

* [PRNG implementation explainer](randomaura-rng-explainer.md)
* [How to access the random seed in a smart contract](accessing-a-random-seed-with-a-smart-contract.md)
* [Randomness FAQs](randomness-faqs.md)

{% hint style="success" %}
The following article explains on-chain randomness functions and how they will be used when POSDAO is fully implemented. It includes concepts and an example, and is a good place to start.

[https://forum.poa.network/t/reliable-randomness-bringing-on-chain-entropy-to-the-xdai-stable-chain/3015](https://forum.poa.network/t/reliable-randomness-bringing-on-chain-entropy-to-the-xdai-stable-chain/3015)
{% endhint %}

## Randomness Contract \(RandomAuRa\) 

RandomAura is an upgradeable contract, so it includes both an implementation and proxy address. To access, utilize the proxy address \(`RandomAuraProxy`\) along with the ABI of the implementation contract \(`RandomAuraCode`\).

| Contract | Address |
| :--- | :--- |
| RandomAuRaCode | 0x77bfEd71b26998Bb9eBd9864e3eC169A5C91504C |
| RandomAuRaProxy | 0x5870b0527DeDB1cFBD9534343Feda1a41Ce47766 |

{% hint style="info" %}
The current implementation requires a chain running Parity's AuRa consensus mechanism with version 2.7.2+. The Random Number generation contract was [introduced in this PR](https://github.com/paritytech/parity-ethereum/pull/10946).
{% endhint %}

