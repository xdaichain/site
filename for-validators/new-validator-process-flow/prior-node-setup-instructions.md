# Prior Node setup instructions

{% hint style="danger" %}
Prior setup steps for a node. These instructions will be updated for POSDAO Validator candidates.
{% endhint %}

{% hint style="warning" %}
If you experience any issues during installation, post your questions in the [https://forum.poa.network/c/xdai-chain/validators-support-private](https://forum.poa.network/c/xdai-chain/validators-support-private).
{% endhint %}

## Setup and configure your Validator Node

### I. Prerequisites of control machine

```text
+---------------------+                  +-------------------------+
|                     |                  |                         |
|     local host      |     ansible      |       remote host       |   
|  (control machine)  +------------------>     (validator node)    |
|                     |                  |                         |
+---------------------+                  +-------------------------+
```

#### **Operating system**

MacOS/Linux-based.

#### **SSH Keys**

{% hint style="success" %}
If you know what ssh keys are, skip this section.
{% endhint %}

1. Check if you already have a keypair:

   ```bash
   ls -la ~/.ssh
   ```

   if you get an error that the directory does not exist or the directory is empty, follow the instructions below. If you already have key pair, you can skip the rest of this section.  

2. Generate new ssh key-pair

   ```bash
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```

   insert your email address and a strong password. By default, keys will be saved to `~/.ssh/` and named `id_rsa` with your public key being `~/.ssh/id_rsa.pub`.

#### **Python**

Check that you have python 2 version &gt;= 2.6.5 or python 3 version &gt;= 3.3 installed

```bash
python --version
```

if not - install using appropriate binary from [here](https://www.python.org/downloads/)

#### **Ansible**

Check that you have ansible version &gt;= 2.3 installed

```bash
ansible --version
```

if not - follow [this guide](http://docs.ansible.com/ansible/latest/intro_installation.html) to install ansible. For example, you can use `pip` to do it:

```bash
sudo pip install ansible
```

#### **Git**

Check that you have git installed

```bash
git --version
```

if not - install it following instructions [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

### II. Validator Node setup

Node setup is at your discretion - criteria are included in the following instructions.

* **Non-AWS Instructions:** Create a node yourself with your favorite hosting provider \(e.g. AWS/Azure/OVH/etc\). 
* **AWS Instructions:** Use our automated playbooks to create a node on AWS \(requires creating an account on AWS\). 

### III. Ansible Playbook Configuration

1. clone repository with ansible playbooks and checkout branch corresponding to xDai:  


   ```bash
   git clone https://github.com/poanetwork/deployment-playbooks.git
   cd deployment-playbooks
   git checkout dai
   ```

2. prepare files with ssh keys \(replace `id_rsa.pub` with your key name\)  


   ```bash
   cat ~/.ssh/id_rsa.pub > files/admins.pub
   cp files/admins.pub files/ssh_validator.pub
   ```

3. create file with configuration settings:  


   ```bash
   cat group_vars/all.yml.network group_vars/validator.yml.example > group_vars/all.yml
   ```

4. edit `group_vars/all.yml` file in your favorite text editor, e.g. `nano`:  


   ```bash
   nano group_vars/all.yml
   ```

Provide the following configuration parameters:

* `NODE_FULLNAME` - enter your organization name \(this will be publicly visible\)
* `NODE_ADMIN_EMAIL` - enter your public email \(this will be publicly visible\)
* `NETSTATS_SERVER` - ask an existing validator \(e.g. POA\) to provide you with correct url of the netstats server 
* `NETSTATS_SECRET` - ask an existing validators \(e.g. POA\) to share the netstats secret code with you or look it up [in the private part of the forum](https://forum.poa.network/t/netstats-server-info/2781) if you already have access. **Do not share it with non-validators or people outside of xDai network**
* `MINING_KEYFILE` - insert _content_ of your mining keystore file here, enclosed in single brackets \(content of json keystore file for your mining key\). The result should look similar to this:

  ```yaml
  MINING_KEYFILE: '{"address":"..."}'
  ```

* `MINING_ADDRESS` - insert your mining key address, e.g.

  ```yaml
  MINING_ADDRESS: "0x..."
  ```

* `MINING_KEYPASS` - insert passphrase from keystore file

In `nano`, to save file and exit, use CTRL+X and then Y

### IV. Running ansible playbook

1\) create a file named `hosts`  from the hosts.example file \(again, using `nano` as an example\)

```bash
cp hosts.example hosts
nano hosts
```

Add only the following content - other fields can be deleted / commented out.  **\(replace 192.0.2.1 with your node's actual ip address\)**:

```text
[validator]
192.0.2.1

[ubuntu]
192.0.2.1 
```

2\)  run ansible playbook, replace path of `--key-file` argument with your desired SSH key

```text
ansible-playbook -i hosts validator.yml -K --key-file "~/.ssh/id_rsa"
```

{% hint style="info" %}
The process should complete successfully. During installation you may be asked to provide sudo password for the user _on remote host_.
{% endhint %}

3\) open [https://dai-netstat.poa.network](https://dai-netstat.poa.network) and check that your node appears on the list and has &gt;0 peers. Wait until it synchronizes with the rest of the blockchain \(block number and block hash should match the rest of the network\).

## Set Metadata

After the approval vote has been finalized by the current validators, you will provide a description of your organization \(metadata\). To set your metadata for the first time, go to [https://validators.poa.network/poa-dapps-validators/set](https://validators.poa.network/poa-dapps-validators/set), connect to xDai chain, and select your **VOTING** key. 

Select **I’m a Company** and provide the full company name and contact email address. Then click **Update metadata** and sign the transaction.

Once this is complete, open [https://blockscout.com/poa/dai](https://blockscout.com/poa/dai) and find a block generated by you \(your mining key\) in the last few blocks. This will be the final confirmation that your node is running and mining blocks. Unless you are also on boarding as a bridge validator, the process is complete!

