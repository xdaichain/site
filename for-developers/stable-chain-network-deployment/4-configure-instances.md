# 4\) Initial Instance Configurations

{% hint style="success" %}
Configure instances after [launching playbooks](3-download-and-configure-playbook.md).
{% endhint %}

1\) Return to root folder of the deployment-playbooks repository

```text
cd ..
```

2\) Copy your ssh public key \(replace `id_rsa.pub` with correct name\)

```text
cat ~/.ssh/id_rsa.pub > files/admins.pub
cp files/admins.pub files/ssh_validator.pub
cp files/admins.pub files/ssh_bootnode.pub
cp files/admins.pub files/ssh_moc.pub
```

3\) Edit `group_vars/all.yml.network` file

* Replace value of `GENESIS_NETWORK_NAME` with name of the network
* replace value of `MOC_ADDRESS` with address of MoC that you generated
* \(optionally\) replace value of `BLK_GAS_LIMIT` to increase/decrease default block gas limit

## **Instance Creation**

{% hint style="info" %}
The following instances will be configured one-by-one. For each instance you will:

1. Create the ansible configuration file using an example file. It will be copied to group\_vars/all.yml
2. Edit the newly created all.yml file with necessary parameters
3. Create a hosts file with the correct instance and ip address
4. Launch the playbook for that instance.
5. Repeat for the next instance.
{% endhint %}

### **Netstat Server**

1\) Create the ****ansible configuration file for netstat node

```text
cat group_vars/all.yml.network group_vars/netstat.yml.example > group_vars/all.yml
```

2\) Edit `group_vars/all.yml`

* Replace value of `NETSTATS_SECRET` with the secret password for netstat server

3\) In the base directory , create a `hosts` file with the following content,  replacing 1.2.3.4 with IP address previously generated for the netstat server.

```text
[netstat]
1.2.3.4

[ubuntu]
1.2.3.4
```

4\) Launch the playbook, it should complete without errors

```text
ansible-playbook -i hosts site.yml
```

{% hint style="success" %}
Open [http://1.2.3.4:3000](http://1.2.3.4:3000/) - you should see an empty dashboard similar to [https://core-netstat.poa.network/](https://core-netstat.poa.network/)
{% endhint %}

### **MoC node**

1\) Create ansible configuration file for moc node

```text
cat group_vars/all.yml.network group_vars/moc.yml.example > group_vars/all.yml
```

2\) Edit `group_vars/all.yml` and change values of the following parameters

* `NODE_FULLNAME` - this name will be displayed in netstat dashboard, e.g. "Master of Ceremony"
* `NODE_ADMIN_EMAIL` - this email will also be displayed in netstat dashboard, e.g. "[moc@example.com](mailto:moc@example.com)"
* `NETSTATS_SERVER` - insert url http://NETSTAT\_IP:3000 of the netstat server
* `NETSTATS_SECRET` - network secret, same as for netstat server
* `MOC_KEYPASS` - password for json keystore file of MoC node
* `MOC_KEYFILE` - here you should include full json string of the keystore file, enclosed in single quotes `'{"version":3,...}'`

3\) Create `hosts` file with the following content, replacing 1.2.3.4 with IP address previously generated for the moc server.

```text
[moc]
1.2.3.4

[ubuntu]
1.2.3.4
```

4\) Launch the playbook, it should complete without errors

```text
ansible-playbook -i hosts site.yml
```

### **Bootnode**

1\) Create ansible configuration file for bootnode

```text
cat group_vars/all.yml.network group_vars/bootnode.yml.example > group_vars/all.yml
```

2\) Edit `group_vars/all.yml` and change values of:

* `NODE_FULLNAME` - this name will be displayed in netstat dashboard, e.g. "Bootnode"
* `NODE_ADMIN_EMAIL` - this email will also be displayed in netstat dashboard, e.g. "[bootnode@example.com](mailto:moc@example.com)"
* `NETSTATS_SERVER` - insert url http://NETSTAT\_IP:3000 of the netstat server
* `NETSTATS_SECRET` - network secret, same as for netstat server

3\) Create `hosts` file with the following content, replacing 1.2.3.4 with IP address previously generated for the bootnode server.

```text
[bootnode]
1.2.3.4

[ubuntu]
1.2.3.4
```

4\) Launch the playbook, it should complete without errors.

```text
ansible-playbook -i hosts site.yml
```

### Validator Nodes

1\) Create ansible configuration file

```text
cat group_vars/all.yml.network group_vars/validator.yml.example > group_vars/all.yml
```

2\) Edit `group_vars/all.yml` and change values:

* `NODE_FULLNAME` - this name will be displayed in netstat dashboard, e.g. "Validator"
* `NODE_ADMIN_EMAIL` - this email will also be displayed in netstat dashboard, e.g. "[validator@example.com](mailto:moc@example.com)"
* `NETSTATS_SERVER` - insert url http://NETSTAT\_IP:3000 of the netstat server
* `NETSTATS_SECRET` - network secret, same as for netstat server
* `MINING_KEYFILE` - content of **validator's** json keystore file, enclosed in single quotes
* `MINING_ADDRESS` - validator address `0x...`
* `MINING_KEYPASS` - password for the keystore file

3\) Create `hosts` file with the following content, substituting the correct ip addresses of validator servers.

```text
[validator]
1.2.3.4

[ubuntu]
1.2.3.4
```

4\) Launch the playbook, it should complete without errors.

```text
ansible-playbook -i hosts site.yml
```

5\) Repeat the process for each validator node - editing the all.yml and hosts file with updated info.

## **Erasing the blockchain state**

This is required to proceed to the next step where you will create a new state.

Login to each of the following nodes

* MoC
* Bootnode
* Validators \(3x\) and do the following:

1\) Stop parity service

```text
sudo systemctl stop poa-parity
```

2\) Erase parity data folder

```text
sudo rm -rf /home/ROLE/parity_data/{network,cache,chains} /home/ROLE/logs/parity.log
```

replacing ROLE with `moc`/`bootnode`/`validator` respectively

{% hint style="info" %}
To ensure services are properly shut down, you can check service status with `sudo systemctl status <servicename>`
{% endhint %}

{% hint style="success" %}
You should now have bootstrapped configuration files.  
  
Next: [Reconfigure Instances](5-reconfigure-instances.md)
{% endhint %}

