# Appendix C: Governance DApps

There are three DApps for governance:

* Ceremony DApp: [https://github.com/poanetwork/poa-dapps-keys-generation](https://github.com/poanetwork/poa-dapps-keys-generation)
* Voting DApp: [https://github.com/poanetwork/poa-dapps-voting](https://github.com/poanetwork/poa-dapps-voting)
* Validators DApp: [https://github.com/poanetwork/poa-dapps-validators](https://github.com/poanetwork/poa-dapps-validators)

Each of these DApps contains a `src/constants.js` script which defines a path to [poa-chain-spec](https://github.com/poanetwork/poa-chain-spec) repo containing the current addresses and ABIs of consensus contracts in the network \(in the corresponding branches: `core` - for `Core` network, `sokol` - for `Sokol` network, `dai` - for `Dai` network\).

In order to use DApp in your network:

1. Fork [poa-chain-spec](https://github.com/poanetwork/poa-chain-spec) repo and create the branch for your network.

   DApps use the following files and directories from `poa-chain-spec`:

   * `abis` \(contains the ABIs of consensus contracts\). Make sure you only have ABI in each `*.abi.json` file \(not combined json obtained by solc compiler\). [The example of the correct .abi.json file](https://github.com/poanetwork/poa-chain-spec/blob/1240457278bbb7157717b642dc0901084c829499/abis/BallotsStorage.abi.json);
   * `contracts.json` \(contains the addresses of consensus contracts and the address of `Master of Ceremony`\).

2. Edit `src/constants.js` and adjust the following:
   * change `constants.organization` to the name of your organization on GitHub;
   * make `constants.NETWORKS` describe your network, e.g.:

     ```text
     constants.NETWORKS = {
       '1234': { // network ID
         NAME: 'NetworkName',
         RPC: 'https://<rpc.address>',  // only for Validators DApp
         BRANCH: 'branch',  // name of the branch in your poa-chain-spec repo
         TESTNET: true  // is it testnet or mainnet? Affects UI colors
       }
     }
     ```

     `constants.NETWORKS` can contain several networks.
3. Launch DApps on your domain names. To host DApps you can use `Netlify` \(`GitHub` account is needed\) or a similar platform.

