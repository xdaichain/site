---
description: xDai gas price recommendations api endpoint
---

# Gas Price Oracle

The BlockScout gas price api endpoint shows a recommended gas price for average, fast and slow transactions based on recently accepted transactions. Users can decide whether to increase the gas price to speed up a transaction or input a lower gas price which may take longer but is still likely to be successful.

* Endpoint: [https://blockscout.com/xdai/mainnet/api/v1/gas-price-oracle](https://blockscout.com/xdai/mainnet/api/v1/gas-price-oracle)
* Response calculated for **previous 200 blocks** and **updated every 5 minutes**.
* Response criteria for average, fast and slow gas estimates follow[ EthGasStation recommendations](https://github.com/ethgasstation/gasstation-express-oracle/blob/master/gasExpress.py#L16-L18).

### Example response

```text
{"average":1.0,"fast":7.5,"slow":1.0}
```

| Response | Denomination | Response Threshold  \(Min gas price per block from previous 200 blocks\) |
| :--- | :--- | :--- |
| average | gwei | 60th percentile of min gas price txs |
| fast | gwei | 90th percentile of min gas price txs \(top 10%\) |
| slow | gwei | 35th percentile of min gas price. |

