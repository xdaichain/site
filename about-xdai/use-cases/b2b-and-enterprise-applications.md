# B2B & Enterprise Applications

_The following assessment materials were compiled by an xDai community member. They provide a basic overview and links designed to help B2B / Enterprise Applications determine if xDai is a good fit for their product offerings. As with any project there are advantages and tradeoffs, and Alexander provides a general overview along with helpful links._

## Evaluating xDai Stable Chain for B2B Use Cases

by [Alexander C](https://github.com/ice09)

The xDai Stable Chain is an Ethereum sidechain with a native stable coin and a bridge to the Ethereum Mainnet for the native currency xDai, which represents DAI on the Ethereum Mainnet.

A native stable coin is a distinctive feature for financial and other Enterprise use cases which could profit from the decentralized aspects of Blockchains, but cannot accept the usage of a highly volatile native crypto currencies.

The xDai Stable Chain is very cheap in transaction fees and very fast, but lacks other features native to the Ethereum Mainnet. This post provides basic information to enable the reader to decide if the xDai Stable Chain can be of use for their prototype or working product.

### Intention

Many respected projects recently migrated from Ethereum to the xDai chain or initially started on xDai. Perpetual Protocol, POAP, Circles UBI, Honeyswap and [many other projects](https://www.xdaichain.com/about-xdai/news-and-information/project-updates/2020-year-in-review) are currently running on xDai. Their main motivations were ease of use, minimal and stable transaction fees and fast transaction times. Some of the projects started on Ethereum, but had their business models upended by the extremely high and unpredictable gas fees. Ethereum tooling \(like Wallets, IDEs, Static Security Analysis, Analytics tools\) is supported due to EVM-compatibility.

### Primary Differences to Ethereum

There are several links with detailed and fair comparisons of Ethereum to xDai \([here](https://defiprime.com/xdai-chain), [here](https://jaredstauffer.medium.com/what-is-xdai-how-do-i-use-xdai-a-simple-explanation-7440cbaf1df6)\).

TL;DR the main differences are

* xDai uses a stable coin as a native currency \(DAI bridged 1:1 from Ethereum\)
* xDai is very cheap in transaction fees.
* xDai is fast: 5 seconds in average block times.
* xDai is less decentralized than the Ethereum Mainnet 1.0. xDai is delegated Proof of Stake vs Ethereum 1.0 Proof of Work consensus.
* xDai uses much less energy for consensus.
* Ethereum roughly has a x100 market cap.
* Ethereum v1 is established and proven to work for more than 6 years. xDai is also proven relative to other L2 solutions, with a working production environment for over 3 years.

### Statistics & Chain Properties

[Blockscout](https://blockscout.com/) is the well known block explorer for POA and related chains like xDai. It is similar to etherscan.io for Ethereum and computes different statistics for xDai and the Sokol Testnet: [https://blockscout.com/xdai/mainnet/](https://blockscout.com/xdai/mainnet/)

| Attribute | Ethereum Mainnet | xDai Stable Chain |
| :--- | :--- | :--- |
| Runtime | EVM | EVM \(100% Ethereum compliant\) |
| Blocktime | ~15 sec. | ~5 sec. |
| Average Gas Costs | &gt;200 gwei \(&gt;&gt; $1\)\* | 1 gwei \(~ $0.000021\) |
| Consensus | PoW \(PoS in Eth2.0\) | POSDAO \(delegated Proof of Stake\) |
| Security Level | PoW with adapting Hashrate, &gt;100bn market cap\* | dPoS with $10M staked\* |

_\*Variable based on market conditions_

### Should I use xDai for my B2B dApp?

This post should help you to do your own risk assessment, as a rule of thumb, these may be guiding principles:

* Running your Smart Contracts on xDai makes them very inexpensive and intuitive to use for you customers \(all prices are stable in USD\).
* Security differs from the Ethereum Mainnet.
* In a financial environment, market-cap differences and incentive structures should be considered when determining the best fit and risk profile.
* xDai provides a ready-made bootstraping environment for prototyping, PoCs, MVPs and more.
* Native stable currency makes xDai distinct from other chains and facilitates use cases not possible on chains with native volatile crypto currencies.

### Sample Use Case: Hashlocked Payment

This brief example should show how easy Smart Contracts can be implemented with a native stable currency.

The contract is instantiated with a recipient address, a hash lock and a value, which is xDai \(wei\), so 100 \* 10^18 is equivalent to $100.

The recipient can now call `conditionalSend` with the correct challenge and will be transferred the stored amount of xDai.

On Ethereum, this could only have been done

* with ETH as currency \(volatile and unpredictable\)
* with DAI as an ERC-20 Token

However, with a ERC-20 Token transfer, the logic of the Smart Contract would have been way more complex and expensive. Complexity adds potential bugs, so arguably it would even be more insecure. For sure, it would be more expensive in Gas fees \(as the call on xDai costs &lt;$0.001\).

This sample should show how easy and straightforward Smart Contract development on xDai can be due to the native stable currency.

```text
contract ConditionalPayment {

    address payable public recipient;
    uint256 public value;
    bytes32 public hashLock;

    event Transferred(address _recipient, uint256 _value);

    constructor(address payable _recipient, bytes32 _hashLock) payable public {
        recipient = _recipient;
        value = msg.value;
        hashLock = _hashLock;
    }

    function conditionalSend(string memory challenge) public {
        if (sha256(abi.encodePacked(challenge)) == hashLock) {
            recipient.transfer(value);
            emit Transferred(recipient, value);
        }
    }
}
```

### Reference List

* [Use Cases](./)
* [Consensus](../../for-validators/consensus/posdao-proof-of-stake-decentralized-autonomous-organization.md)
* [Fiat Gateway](../../for-users/get-xdai-tokens/buying-xdai-with-fiat/ramp-network.md)
* [Current Validators](../../for-validators/about-xdai-validators/original-xdai-validators/)
* [Incentives](../../for-stakers/stake-token/)
* [Block Explorer](https://blockscout.com/xdai/mainnet/)
* [Wallets](../../for-users/wallets/)
* [FAQs](../faqs/)

