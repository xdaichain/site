# 6\) Configure Bootnode Instance

## Bootnode

1\)  Connect to the Bootnode instance and replace the `spec.json` file at `/home/bootnode/spec.json` with the `spec.json` from the MoC instance.

2\) Replace the `bootnodes.txt` file at `/home/bootnode/bootnodes.txt` with the `bootnodes.txt` file from the MoC instance.

3\) Restart Parity: `sudo systemctl restart poa-parity`

4\) Retrieve bootnode's enode: open `/home/bootnode/logs/parity.log` and find at its beginning a line with the enode - that should look like this:

```text
Public node URL: enode://c7dfb42206db1893d1ab0cbbfcb801ffe7e45b88d05f19abe3c6169d88078d17bd4442d5ca3d3a6818e011872102b88c871d33bc29ed8088cf66802a667247c6@192.168.10.106:30303
```

5\) Add the enode to `bootnodes.txt` file. You will now have 2 entries, one for the MoC and a second for the bootnode. Save the file.

6\) **Log back into MoC node** and replace the `/home/moc/bootnodes.txt` file with the `bootnodes.txt` file from the Bootnode. It should contain both enode entries. Save the file and restart MoC node with `sudo systemctl restart poa-parity`.

7\) Go to netstat dashboard and make sure MoC node and bootnode are show there and display the same hashes for each block.

{% hint style="success" %}
[Next: Call Contract Methods](7-call-contract-methods-using-mycrypto.md) 
{% endhint %}



