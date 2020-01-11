# 9\) Bridge Deployment

{% hint style="success" %}
Deploy the bridge after you have [reconfigured your instance](5-reconfigure-instances.md).
{% endhint %}

## Create additional accounts for deployment

1\) Generate private keys for the following using MetaMask or MyEtherWallet. Save as **json keystore file + password**. Note the json location,  wallet address, and password for each account.

* DEPLOYMENT\_ACCOUNT
* FOREIGN\_ADMIN\_BRIDGE
* FOREIGN\_ADMIN\_VALIDATOR
* FOREIGN\_OWNER
* HOME\_ADMIN\_BRIDGE
* HOME\_ADMIN\_VALIDATOR
* HOME\_OWNER
* VALIDATOR

{% hint style="warning" %}
This data can not be recovered through an account after creation, so be sure to store accurately and safely.
{% endhint %}

{% hint style="info" %}
You will need tokens for deployment on the Foreign side of the bridge. This means the DEPLOYMENT\_ACCOUNT and VALIDATOR accounts will require tokens. The DEPLOYMENT\_ACCOUNT will deploy bridge contracts and initialize the bridge, and VALIDATOR accounts use tokens to pay for txs on the foreign side.
{% endhint %}

2\) Add addresses to the Certifier contract using the [MyCrypto method described previously](5-reconfigure-instances.md#call-contract-methods-using-mycrypto).

a\) Use the `Master of Ceremony` address to call the `certify` method in the `Certifier` Contract. You will certify the following addresses, completing a separate transaction for each:

* VALIDATOR
* DEPLOYMENT\_ACCOUNT
* HOME\_OWNER

Certifier ABI: [https://raw.githubusercontent.com/parity-contracts/name-registry/master/abis/SimpleCertifier.json](https://raw.githubusercontent.com/parity-contracts/name-registry/master/abis/SimpleCertifier.json)

## Configure and Deploy Bridge Contracts

1\) Clone the Repo

```text
git clone -b develop https://github.com/poanetwork/tokenbridge-contracts.git
cd tokenbridge-contracts
```

2\) Copy the following example to create the `deploy/.env` file. The example uses the DAI Stablecoin for the ERC20\_Token\_Address.  [Mainnet](https://etherscan.io/token/0x89d24a6b4ccb1b6faa2625fe562bdd9a23260359) \| [Kovan](https://kovan.etherscan.io/address/0xc4375b7de8af5a38a93548eb8453a498222c4ff2)

{% hint style="warning" %}
Replace all variables templated with tags \(&lt;&gt;\) with actual values.
{% endhint %}

{% hint style="warning" %}
Learn more about variables here: [https://github.com/poanetwork/poa-bridge-contracts/blob/master/deploy/README.md](https://github.com/poanetwork/poa-bridge-contracts/blob/master/deploy/README.md)
{% endhint %}

```text
 BRIDGE_MODE=ERC_TO_NATIVE
 DEPLOYMENT_ACCOUNT_PRIVATE_KEY=<DEPLOYMENT_ACCOUNT_PRIVATE_KEY>
 DEPLOYMENT_GAS_LIMIT=5000000
 HOME_DEPLOYMENT_GAS_PRICE=0
 FOREIGN_DEPLOYMENT_GAS_PRICE=10000000000
 GET_RECEIPT_INTERVAL_IN_MILLISECONDS=3000
 #long name
 BRIDGEABLE_TOKEN_NAME=TEST
 #short name
 BRIDGEABLE_TOKEN_SYMBOL=Test
 BRIDGEABLE_TOKEN_DECIMALS=18

 HOME_RPC_URL=https://<url.to.homenet>
 HOME_BRIDGE_OWNER=<HOME_OWNER>
 HOME_VALIDATORS_OWNER=<HOME_ADMIN_VALIDATOR>
 HOME_UPGRADEABLE_ADMIN=<HOME_ADMIN_BRIDGE>

 HOME_DAILY_LIMIT=30000000000000000000000000
 HOME_MAX_AMOUNT_PER_TX=1500000000000000000000000
 HOME_MIN_AMOUNT_PER_TX=500000000000000000
 HOME_REQUIRED_BLOCK_CONFIRMATIONS=1
 HOME_GAS_PRICE=0

 FOREIGN_RPC_URL=https://<url.to.foreignnet>
 FOREIGN_BRIDGE_OWNER=<FOREIGN_OWNER>
 FOREIGN_VALIDATORS_OWNER=<FOREIGN_ADMIN_VALIDATOR>
 FOREIGN_UPGRADEABLE_ADMIN=<FOREIGN_ADMIN_BRIDGE>
 FOREIGN_DAILY_LIMIT=15000000000000000000000000
 FOREIGN_MAX_AMOUNT_PER_TX=750000000000000000000000
 FOREIGN_MIN_AMOUNT_PER_TX=500000000000000000
 FOREIGN_REQUIRED_BLOCK_CONFIRMATIONS=8
 FOREIGN_GAS_PRICE=18000000000

 #for bridge erc_to_erc and erc_to_native mode
 #mainnet
 ERC20_TOKEN_ADDRESS=0x89d24a6b4ccb1b6faa2625fe562bdd9a23260359
 #kovan
 #ERC20_TOKEN_ADDRESS=0xc4375b7de8af5a38a93548eb8453a498222c4ff2
 #validators
 REQUIRED_NUMBER_OF_VALIDATORS=1
 #If several validators are used, list them separated by space without quotes
 #E.g. VALIDATORS=0x 0x 0x
 VALIDATORS=<address of validator>

 HOME_REWARDABLE=false
 FOREIGN_REWARDABLE=false
 DEPLOY_REWARDABLE_TOKEN=false
```

3\) Deploy Contracts

```text
npm i
npm run compile
cd deploy
npm i
node deploy.js
```

{% hint style="success" %}
Next: [Deploy Consensus Contracts](7-deploy-consensus-contracts-on-moc-node.md)
{% endhint %}

