# 10\) Finalize Deployment

1\) Remove initial keys, deployment account's address, and HomeOwner's address from `Certifier` contract calling its `revoke` method. [How to call contract's method with MyCrypto.](5-reconfigure-instances.md#call-contract-methods-using-mycrypto)

2\) Launch bridge oracles \([https://github.com/poanetwork/tokenbridge/tree/master/deployment](https://github.com/poanetwork/tokenbridge/tree/master/deployment)\).

3\) Call `setFee(1000000000000000000)` method of `Registrar` contract to restore previously zeroed fee.

