# STAKE Staking Token

{% hint style="info" %}
STAKE is a flexible asset, meaning it may be used in a variety of contexts. The initial use case describes leveraging STAKE in the POSDAO implementation for xDai, however STAKE may be used for staking \(or other purposes\) by other blockchain networks. 
{% endhint %}

{% hint style="success" %}
STAKE token address on Ethereum [0x0Ae055097C6d159879521C384F1D2123D1f195e6](https://etherscan.io/token/0x0Ae055097C6d159879521C384F1D2123D1f195e6)
{% endhint %}

STAKE is a new ERC20 token designed to secure the on-chain payment layer and provide a mechanism for validators to receive multiple POS incentives. It is an ERC20 staking token with a market driven value. 

The initial supply of 8.5375M STAKE tokens will be released over time. Additional tokens are minted as rewards at the conclusion of each staking epoch. 

Users \(stakers\) provide STAKE as collateral when participating in the consensus process. In exchange for providing STAKE \(and supporting a node\), users receive multiple rewards. The primary reward is in the form of additional STAKE tokens.

* **STAKE rewards**: STAKE is minted as a reward based on the amount of STAKE placed in the protocol. The final emission rate is TBD through a risk assessment and community review. Target range: ~15% APR.   A STAKE transfer fee is also assessed when a user removes their STAKE from the xDai chain \(using an [AMB bridge](https://docs.tokenbridge.net/amb-bridge/about-amb-bridge) extension\). This fee is distributed as a reward to participating stakers. 
* **xDAI rewards**: DAI locked in the bridge is converted to CHAI, which earns additional interest on the locked amount. This interest is distributed in xDai to stakers at the end of a staking epoch. 
* **EXIT rewards**: EXIT tokens are minted and distributed to stakers at the end of each epoch. This exploratory virtual stable currency has a stable face value 1:1 with the US Dollar. EXIT rewards may be introduced at the beginning of the protocol or later on.

### Staking STAKE

When the xDai DPOS protocol starts, individuals who own STAKE tokens can place them into the protocol through a user friendly interface. Functionality includes an [AMB Bridge extension](https://docs.tokenbridge.net/amb-bridge/about-amb-bridge) which allows users to move STAKE tokens between the Ethereum mainnet and the xDai chain.

In addition, exchanges may offer the opportunity to provide delegator staking directly from the exchange. Typically, this means STAKE holders select the option to stake the token, and the exchange processes the request \(determining which validator to stake on, aggregating rewards and other tasks for a small percentage fee\). Staking functionality is initiated by the participating exchange. 

Validator candidates must meet certain requirements before placing STAKE \(the ability to run a functional node and minimum STAKE amounts\).  Delegators can place additional STAKE on candidates and receive rewards when the candidates they have placed STAKE on are chosen as validators.

When STAKE is locked in the protocol, rewards for sealing blocks are generated in STAKE, xDai and EXIT. In addition, fees for removing STAKE from the xDai chain are assessed and distributed among active stakers.

### STAKE Total Supply 

The STAKE circulating supply is **8,537,500 tokens** \(once all tokens are unlocked in the protocol\).

### Deployed STAKE Contracts

Contracts corresponding to STAKE and distribution roles have been deployed to the Ethereum Mainnet. All contracts are verified in Etherscan.

| Contract Type | Address |
| :--- | :--- |
| **STAKE Token** | [0x0Ae055097C6d159879521C384F1D2123D1f195e6](https://etherscan.io/address/0x0Ae055097C6d159879521C384F1D2123D1f195e6) |
| **Distribution Contract \(DC\)** _Prepares available withdrawal amounts in Investor/Fund Contracts_ | [0x9BC4a93883C522D3C79c81c2999Aab52E2268d03](https://etherscan.io/address/0x9bc4a93883c522d3c79c81c2999aab52e2268d03) |

Funds in contracts below are available according to the release schedule \(e.g. a certain % is released each day\). The Distribution Contract is called with the corresponding number value below \(e.g. 3 for private offering\) to prepare/initialize funds for withdrawal. Once initialized, fund participants can pull available amounts to their wallets. A UI will be released shortly, the process is explained in detail in the [Getting STAKE tokens](getting-stake-tokens-1/claiming-stake-tokens.md) section.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Investor / Fund Contracts</th>
      <th style="text-align:left">Address</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>(1) Ecosystem Fund</b>
        </p>
        <p><em>Begins 336 days post listing, continues daily for 336 days </em>
        </p>
      </td>
      <td style="text-align:left"><a href="https://etherscan.io/address/0x86edd0c110d1fc7f8a5e1108623b3b1b4e3740f9">0x86edd0c110D1Fc7F8A5e1108623b3B1B4E3740f9</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>(2) Public Offering </b>
        </p>
        <p><em>100% released at listing</em>
        </p>
      </td>
      <td style="text-align:left"><a href="https://etherscan.io/address/0x0df05adac0159e215111696339ad4998e5871b3d">0x0DF05ADaC0159e215111696339AD4998e5871B3D</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>(3) Private Offering</b>
        </p>
        <p>25% released at listing (492,737.75)
          <br />10% at day 28
          <br />65% daily for next 224 days</p>
      </td>
      <td style="text-align:left"><a href="https://etherscan.io/address/0x3cFE51b61E25750ab1426b0072e5D0cc5C30aAfA">0x3cFE51b61E25750ab1426b0072e5D0cc5C30aAfA</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>(4) Advisor</b>
        <br /><em>Begins 84 days post listing Daily for 252 days</em>
      </td>
      <td style="text-align:left"><a href="https://etherscan.io/address/0x0218B706898d234b85d2494DF21eB0677EaEa918">0x0218B706898d234b85d2494DF21eB0677EaEa918</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>(5) Foundation Reward</b>
        <br /><em>Begins 84 days post listing, Daily for 252 days</em>
      </td>
      <td style="text-align:left"><a href="https://etherscan.io/address/0x86edd0c110d1fc7f8a5e1108623b3b1b4e3740f9">0x86edd0c110D1Fc7F8A5e1108623b3B1B4E3740f9</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>(6) Liquidity Fund</b>
        </p>
        <p>100% released at listing</p>
      </td>
      <td style="text-align:left"><a href="https://etherscan.io/address/0x0df05adac0159e215111696339ad4998e5871b3d">0x0DF05ADaC0159e215111696339AD4998e5871B3D</a>
      </td>
    </tr>
  </tbody>
</table> 

