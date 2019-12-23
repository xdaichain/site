# Appendix D: Call Contract Methods using MyCrypto

{% hint style="info" %}
This example is taken from [5\) Reconfigure Instances](5-reconfigure-instances.md#call-contract-methods-using-mycrypto). Once connection is established, you can skip to step 5 below.
{% endhint %}

1\) Set a temporary zero fee in the `Registry` contract for registering addresses at the bootnode rpc.

 a\) Check the bootnode ip is accessible in a browser.   
Visit [https://1.2.3.4 ](https://1.2.3.4%20) \(using the bootnode's ip address\). You may see a warning that the certificate is invalid. Click **Advanced** and proceed and unlock the browser. You should now see a message like "**Used HTTP Method is not allowed. POST or OPTIONS is required**". This means the bootnode is ready for the next step.

![Click to Proceed and unlock the url](../../.gitbook/assets/unsafe-1.png)

2\) Go to [https://legacy.mycrypto.com/](https://legacy.mycrypto.com/#contracts) in Google Chrome

3\) Click on the network in the top right and select Add Custom Network/Node

![](../../.gitbook/assets/add-custom.png)

4\) Fill in information about your node. 

1. Node name can be your choice 
2. url is https://1.2.3.4 \(using your bootnode ip\)
3. Keep currency as ETH
4. Save and Use Custom Node

{% hint style="info" %}
If you are experiencing issues connecting, set your web3 wallet \(metamask\) to the same https://1.2.3.4  bootnode network.
{% endhint %}

![](../../.gitbook/assets/custom-2.png)

5\) Set gas price to 0. 

* Open context menu \(right click\) for the `Gas Price` slider and choose `Inspect`
* Change the value of `min` attribute of `input` html tag to `0` :
* Close Chrome Developer Tools. Now, you can set zero gas price in the slider

![](../../.gitbook/assets/0gas.gif)

6\) Go to the Contracts Tab. Enter in the **Registry Contract Address** and the **ABI for the Registrar Contract**. 

ABI is located here: [https://raw.githubusercontent.com/parity-contracts/name-registry/master/abis/SimpleRegistry.json](https://raw.githubusercontent.com/parity-contracts/name-registry/master/abis/SimpleRegistry.json)

![](../../.gitbook/assets/access1.png)

7\) Select the `setFee` method using the MoC key. Under How to Access, use the json/Keystore file option to connect to your MOC keystore. Set the `_amount` to 0.

![](../../.gitbook/assets/contract-2.png)

8\) Submit the transaction. Fill in the default value for Gas, it may be adjusted \(here the default was 30000 adjusted to 21400.

![](../../.gitbook/assets/submit-trans.png)



