# 3\) Download & Launch Playbooks

{% hint style="success" %}
Complete [1\) Local Tooling Setup](local-tooling-setup.md) and [2\) AWS Initial Setup ](aws-initial-setup.md)before proceeding.
{% endhint %}

## Prerequisites

1. Generate private keys for the Master of Ceremony \(MoC\) and 3 Validator accounts \(4 accounts total\). Use MetaMask or myetherwallet to generate private keys and save as **json keystore file + password**. Note the json location,  wallet address, and password for each file.
2. Choose and write down a name for the future Network \(Genesis Network Name\).
3. Choose and write down a secret password for the Netstat Server.

{% hint style="info" %}
Record and keep this information handy for installation:

* MoC wallet address 
* MoC wallet password
* Validator wallet addresses
* Validator wallet passwords
* Genesis Network Name
* Netstat Password

**From AWS Setup:**

* AWS user name 
* AWS Access key ID
* AWS Secret access key
* AWS keypair\_name
{% endhint %}

## Download & Launch \(to create AWS instances\)

1\) Clone repositories with playbooks. [https://github.com/poanetwork/deployment-playbooks](https://github.com/poanetwork/deployment-playbooks)

```text
git clone https://github.com/poanetwork/deployment-playbooks.git
```

2\) Switch to aws directory.

```text
cd deployment-playbooks/aws
```

3\) Create configuration file. Start with the Netstat server

```text
cp group_vars/all.yml.example group_vars/all.yml
```

4\) Edit `all.yml`, replacing the following parameters:

```text
access_key: your-AWS-access-key
secret_key: your-AWS-secret-key

awskeypair_name: "keypairname"
region: "us-east-1"
vpc_id: "vpc-ID-number"
vpc_subnet_id: "subnet-ID-number"
```

{% hint style="info" %}
Depending on your resource needs \(or for testing purposes\) you can save costs by changing all instances of "t2.large" to "t2.small"
{% endhint %}

5\) Launch the netstat playbook

```text
ansible-playbook netstat.yml
```

It should complete without errors, and a new instance created in AWS EC2.  You will see the new node's IP address in the logs. Write it down \(you can also retrieve from AWS later if needed\).

{% hint style="warning" %}
If you get the following error, try adding a private-key flag to the command.   
  
fatal: \[ip.address\]: UNREACHABLE! =&gt; {"changed": false, "msg": "SSH Error: data could not be sent to remote host \"ip.address\". Make sure this host can be reached over ssh", "unreachable": true}

```text
ansible-playbook netstat.yml --private-key=~/.ssh/your-private-key
```
{% endhint %}

6\) Repeat the same process for MoC, Explorer and Bootnode playbooks.

```text
ansible-playbook moc.yml
ansible-playbook explorer.yml
ansible-playbook bootnode.yml
```

7\) For validator nodes, change the value of validator\_instance\_name for each new validator.

```text
ansible-playbook validator.yml -e "validator_instance_name=validator-1"
ansible-playbook validator.yml -e "validator_instance_name=validator-2"
ansible-playbook validator.yml -e "validator_instance_name=validator-3"
```

{% hint style="success" %}
You should now have 7 nodes running on AWS: 1x for future MoC, 1x netstat, 1x explorer \(etherchain light\), 1x bootnode, 3x validators.  
  
 Next: [Configure Instances](4-configure-instances.md).
{% endhint %}

## 

