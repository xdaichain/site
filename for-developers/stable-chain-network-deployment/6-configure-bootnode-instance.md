# 6\) Configure Bootnode Instance

## Bootnode

1\)  Connect to the Bootnode instance and replace the `spec.json` file at `/home/bootnode/spec.json` with the `spec.json` from the MoC instance.

2\) Replace the `bootnodes.txt` file at `/home/bootnode/bootnodes.txt` with the `bootnodes.txt` file from the MoC instance.

3\) Open `/home/bootnode/node.toml` in your favorite editor and add `"parity"` to the `apis` option in `[rpc]` section so that it would look like `apis = ["web3","eth","net","parity"]`

4\) Restart Parity: 

```text
sudo systemctl restart poa-parity && sleep 10 && sudo systemctl restart poa-netstats
```

5\) Retrieve bootnode's enode with this command:

```text
curl --data '{"method":"parity_enode","params":[],"id":1,"jsonrpc":"2.0"}' -H "Content-Type: application/json" -X POST localhost:8545
```

6\) Add the `enode` from json result to `bootnodes.txt` file. You will now have 2 entries, one for the MoC and a second for the bootnode. Save the file.

7\) Open `/home/bootnode/node.toml` in your favorite editor and remove `"parity"` from the `apis` option in `[rpc]` section.

8\) Restart Parity & Netstats: 

```text
sudo systemctl restart poa-parity && sleep 10 && sudo systemctl restart poa-netstats
```

9\) **Log back into MoC node** and replace the `/home/moc/bootnodes.txt` file with the `bootnodes.txt` file from the Bootnode. It should contain both enode entries. Save the file and restart MoC node / Netstats with:

```text
sudo systemctl restart poa-parity && sleep 10 && sudo systemctl restart poa-netstats
```

10\) Go to the Netstat dashboard and make sure MoC node and Bootnode are shown and display the same hashes for each block.

{% hint style="success" %}
[Next: Call Contract Methods](7-call-contract-methods-using-mycrypto.md) 
{% endhint %}



