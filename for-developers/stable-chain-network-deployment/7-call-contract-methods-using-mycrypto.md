# 7\) Call Contract Methods using MyCrypto

Next you will set a temporary zero fee in the `Registry` contract for registering addresses at the bootnode rpc.

 a\) Check the bootnode ip is accessible in a browser.   
Visit [https://1.2.3.4 ](https://1.2.3.4%20) \(using the bootnode's ip address\). You may see a warning that the certificate is invalid. Click **Advanced** and proceed and unlock the browser. You should now see a message like "**Used HTTP Method is not allowed. POST or OPTIONS is required**". This means the bootnode is ready for the next step.

![Click to Proceed and unlock the url](../../.gitbook/assets/unsafe-1.png)

2\) Go to [https://legacy.mycrypto.com/](https://legacy.mycrypto.com/#contracts) in Google Chrome

3\) Click on the network in the top right and select Add Custom Network/Node

![](../../.gitbook/assets/add-custom.png)

4\) Fill in information about your node. 

1. Node name can be your choice 
2. URL is https://1.2.3.4 \(using your bootnode ip\)
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

9\) Repeat the process above  to call the `reserve`  & `setAddress` methods

* `Master of Ceremony` should first call `reserve` method with `_name = 0x6d3815e6a4f3c7fcec92b83d73dda2754a69c601f07723ec5a2274bd6e81e155` \( enter verbatim, this is the keccak hash of  `"service_transaction_checker"`.
* Then call `setAddress` method with:
  * \_name = `0x6d3815e6a4f3c7fcec92b83d73dda2754a69c601f07723ec5a2274bd6e81e155`,
  * \_key = `A` 
  * \_value = `0xCERTIFIER_CONTRACT_ADDRESS`

{% hint style="info" %}
ABI Resources:

ABI of `Registrar` contract: [https://raw.githubusercontent.com/parity-contracts/name-registry/master/abis/SimpleRegistry.json](https://raw.githubusercontent.com/parity-contracts/name-registry/master/abis/SimpleRegistry.json)

ABI of `Certifier` contract: [https://raw.githubusercontent.com/parity-contracts/name-registry/master/abis/SimpleCertifier.json](https://raw.githubusercontent.com/parity-contracts/name-registry/master/abis/SimpleCertifier.json)
{% endhint %}

{% hint style="success" %}
Next: [Update spec.json file](8-update-spec.json-file.md)
{% endhint %}

