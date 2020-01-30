# 13\) Finalize Deployment

{% hint style="success" %}
Congratulations - you are ready to complete the deployment! Follow the steps below to finalize your deployment. For additional info and features, see the Appendices:

* [Appendix A: BlockScout Explorer](appendix-a-blockscout-explorer.md)
* [Appendix B: Bridge UI](appendix-b-launching-bridge-ui.md)
* [Appendix C: Governance DApps](appendix-c-governance-dapps.md)
{% endhint %}

1\) Remove initial keys, deployment account's address, and HomeOwner's address from `Certifier` contract calling its `revoke` method. [How to call contract's method with MyCrypto.](appendix-d-call-contract-methods-using-mycrypto.md)

2\) Launch bridge oracles \([https://github.com/poanetwork/tokenbridge/tree/master/deployment](https://github.com/poanetwork/tokenbridge/tree/master/deployment)\).

3\) Call `setFee(1000000000000000000)` method of `Registrar` contract to restore previously zeroed fee.

