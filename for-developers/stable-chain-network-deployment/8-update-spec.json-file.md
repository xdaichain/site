# 8\) Update spec.json file

1\) Update `spec.json` on both **MoC node** and **rpc bootnode.**

* Stop Parity

```text
sudo systemctl stop poa-parity
```

* Add `Registrar` contract address into `params` section of `spec.json`. Make sure it is the appropriate params section.

  ```text
    "name": "...",
    "engine": {
      ...
    },
    "params": {
      ...,
      "NetworkID": "xxx",
      ...,
      "registrar": "0xREGISTRAR_ADDRESS"
    },
    ...
  ```

2\) Restart Parity on both nodes.

```text
sudo systemctl restart poa-parity && sleep 10 && sudo systemctl restart poa-netstats
```

3\) Check Netstat to ensure your nodes are communicating. They should display the same block hash for each block.

Open [http://1.2.3.4:3000](http://1.2.3.4:3000/) \(using your Netstats url instance\) to check your nodes.

{% hint style="success" %}
Next: [Bridge Deployment](bridge-deployment.md)
{% endhint %}

