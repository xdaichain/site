---
description: Rebasing and Inflationary tokens
---

# Exceptions and Special Cases

While most tokens can be freely transferred between chains, there are several exceptions where token properties create bridge-related issues.

* Bridge operations are disabled for [Rebasing tokens](exceptions.md#rebasing-tokens). 
* [Inflationary tokens](exceptions.md#inflationary-eth-2-0-staking-tokens) can still be bridged, but any accrued inflation IS NOT returned to the user upon bridge exit. 

## Rebasing Tokens

Rebasing tokens include an elastic function where supply can be increased or decreased at regular intervals. If these tokens are bridged, supply impacts could result in inequities on either side of the bridge. In some cases this could result in a bridge balance reduction and the inability for users to exit.

To prevent this, we have disabled bridging capability for rebasing type tokens. A partial token list is included below.



| Name | Symbol | Address |
| :--- | :--- | :--- |
| Ampleforth | AMPL | 0xd46ba6d942050d489dbd938a2c909a5d5039a161 |
| DIGG | DIGG | 0x798d1be841a82a273720ce31c822c61a67a601c3 |
| Auric Network | AUSCM | 0x1c7bbadc81e18f7177a95eb1593e5f5f35861b10 |
| Benchmark Protocol | MARK | 0x67c597624b17b16fb77959217360b7cd18284253 |
| Based Money | $BASED | 0x68a118ef45063051eac49c7e647ce5ace48a68a5 |
| rbase.finance | RBASE | 0xe8b251822d003a2b2466ee0e38391c2db2048739 |
| Ditto | DITTO | 0x233d91a0713155003fc4dce0afa871b508b3b715 |
| Base Protocol | BASE | 0x07150e919b4de5fd6a63de1f9384828396f25fdc |
| USDf | USDf | 0x05462671c05adc39a6521fa60d5e9443e9e9d2b9 |
| xBTC | XBTC | 0xecbf566944250dde88322581024e611419715f7a |
| Debase | DEBASE | 0x9248c485b0b80f76da451f167a8db30f33c70907 |
| Coil | COIL | 0x3936ad01cf109a36489d93cabda11cf062fd3d48 |
| Dollars | USDX | 0x2f6081e3552b1c86ce4479b80062a1dda8ef23e3 |
| RMPL | RMPL | 0xe17f017475a709de58e976081eb916081ff4c9d5 |
| Rebased | REB2 | 0x87f5f9ebe40786d49d35e1b5997b07ccaa8adbff |
| VELO Token | VLO | 0x98ad9b32dd10f8d8486927d846d4df8baf39abe2 |
| Tokens of Babel | TOB | 0x7777770f8a6632ff043c8833310e245eba9209e6 |
| Rise Protocol | RISE | 0x3fa807b6f8d4c407e6e605368f4372d14658b38c |
| Soft Link | SLINK | 0x10bae51262490b4f4af41e12ed52a0e744c1137a |
| Ramifi Protocol | RAM | 0xac6fe9aa6b996d15f23e2e9a384fe64607bba7d5 |
| GRPL Finance | GRPL | 0x15e4132dcd932e8990e794d1300011a472819cbd |
| Xdef Finance | XDEF2 | 0x5166d4ce79b9bf7df477da110c560ce3045aa889 |
| Antiample | XAMP | 0xf911a7ec46a2c6fa49193212fe4a2a9b95851c27 |

## Inflationary \(Eth 2.0 Staking\) Tokens

Inflationary tokens accrue additional value over time. While they are locked in the bridge contract this value will accrue, but will remain on the balance of the bridge upon exit. **Inflation will not be returned to a user's balance.** This maintains the 1 to 1 ratio of bridged tokens necessary for OmniBridge functionality.

Users are free to bridge these tokens but need to be aware that any accrued inflation will not be added to their balances. Usage of the accumulated inflation will be determined at a later time by bridge governors.

 A partial token list of inflationary tokens is included below.

| name | symbol | address |
| :--- | :--- | :--- |
| Lido Staked Ether | stETH | 0xae7ab96520de3a18e5e111b5eaab095312d7fe84 |
| StakeHound Staked Ether | STETH | 0xdfe66b14d37c77f4e9b180ceb433d1b164f0281d |
| ankrETH | AETH | 0xe95a203b1a91a908f9b9ce46459d101078c2c3cb |
| Cream ETH 2 | CRETH2 | 0xcbc1065255cbc3ab41a6868c22d1f1c573ab89fd |
| Binance ETH staking | BETH | 0x250632378e573c6be1ac2f97fcdf00515d0aa91b |

