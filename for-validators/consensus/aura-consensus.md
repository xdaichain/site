---
description: 'Current xDai Consensus model: POSDAO with Authority Round Consensus'
---

# AuRa with POSDAO Consensus

Consensus refers to the agreement process between nodes in a network. The nodes must agree on which transactions to include in the next block on the chain before these transactions are committed

xDai currently uses Parity's AuRa \(Authority Round\) proof-of-authority consensus model to append blocks to the xDai chain. In this model, selected validators \([selected through the POSDAO process](posdao-proof-of-stake-decentralized-autonomous-organization.md)\) take turns signing blocks. A signed block is broadcast to all validators, and if the majority agree it is valid, it is added to the chain. A new block is added every 5 seconds, regardless of whether any transactions occurred during that time. 

View current xDai validators \(change network dropdown to xDai Stable Chain\): [https://validators.poa.network/poa-dapps-validators](https://validators.poa.network/poa-dapps-validators) 

### Additional Information on AuRa:

{% embed url="https://wiki.parity.io/Aura" %}

