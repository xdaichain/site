# 7\) Deploy Consensus Contracts \(on MoC node\)

{% hint style="success" %}
Deploy consensus contracts after [Bridge Deployment](bridge-deployment.md)
{% endhint %}

1\) Clone the repo into the moc folder \(`:/home/moc`\)

```text
git clone https://github.com/poanetwork/poa-network-consensus-contracts
cd poa-network-consensus-contracts
npm i
```

2\) Set `gasPrice` to `0` in `truffle.js`

```text
diff --git a/truffle.js b/truffle.js
index d76a15e..8edbdaf 100644
--- a/truffle.js
+++ b/truffle.js
@@ -25,6 +25,7 @@ module.exports = {
       host: "localhost",
       port: 8545,
       gas: 6400000,
+      gasPrice: "0",
       network_id: "*" // Match any network id
     },
   },
```

3\) Edit `contracts/RewardByBlock.sol`

* set `blockRewardAmount` to `0`
* set `emissionFundsAmount` to `0`
* set `bridgesAllowedLength` to `1`
* set the address of bridge contract in `bridgesAllowed()` function  use the  `homeBridge` address from previous step, it is located in poa-bridge-contracts/bridgeDeploymentResults.json

**Example:**

```text
// These values must be changed before deploy
uint256 public constant blockRewardAmount = 0 ether; 
uint256 public constant emissionFundsAmount = 0 ether;
address public constant emissionFunds = 0x0000000000000000000000000000000000000000;
uint256 public constant bridgesAllowedLength = 1;

...

function bridgesAllowed() public pure returns(address[bridgesAllowedLength]) {
    // These values must be changed before deploy
    return([
        address(0xBRIDGE_CONTRACT_ADDRESS)
    ]);
}
```

4\) Deploy Contracts

```text
$ DEPLOY_POA=true SAVE_TO_FILE=true MASTER_OF_CEREMONY=0xMASTER_OF_CEREMONY ./node_modules/.bin/truffle migrate --reset --network sokol
```

## Set the RewardByBlock Contract Address

1\) Launch `tokenbridge-contracts/deploy/src/utils/setBlockReward.js.` The `0xBLOCK_REWARD` is located in the `poa-network-consensus-contracts/contracts.json` file.

```text
HOME_BRIDGE_ADDRESS=0xHOME_BRIDGE_CONTRACT_ADDRESS BLOCK_REWARD_ADDRESS=0xBLOCK_REWARD  DEPLOYMENT_ACCOUNT_PRIVATE_KEY=HOME_OWNER_PRIVATE_KEY node deploy/src/utils/setBlockReward.js
```

## Update `spec.json` to create a Hard Fork

1\) Add the addresses of `PoaNetworkConsensus` and `RewardByBlock` contracts \(making hard fork\).

* Add a number of hard fork's transition block and the address of `PoaNetworkConsensus` contract to `engine.authorityRound.params.validators.multi` section, add `blockRewardContractAddress` and `blockRewardContractTransition` params to `engine.authorityRound.params` section:

{% hint style="info" %}
Change `1234` to the number of a future block.
{% endhint %}

```text
"validators": {
  "multi": {
    "0": {
      "list": [
        "0xMASTER_OF_CEREMONY"
      ]
    },
    "1234": {
      "safeContract": "0xPOA_NETWORK_CONSENSUS_ADDRESS(POA_ADDRESS)"
    }
  }
},
 "blockRewardContractAddress": "0xBLOCK_REWARD_ADDRESS",
 "blockRewardContractTransition": 1243
```

2\) Restart Parity on Moc Node

```text
sudo systemctl restart poa-parity
```

and wait until the hard fork's block number is reached and `RewardByBlock` is activated.

3\) Replace the updated `spec.json` on all the other network nodes \(bootnode, explorer, validators\) and reboot them. Also update the `spec.json` on the rpc bootnode launched earlier and reboot.

{% hint style="success" %}
Next: [Generate Keys](generate-keys.md)
{% endhint %}



