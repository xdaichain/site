---
description: Using automated playbooks to create a node on AWS (requires AWS account)
---

# AWS Node Deployment using Playbooks

{% hint style="warning" %}
The following instructions use previously developed ansible playbooks which are not currently maintained by the xDai team. Use at your own risk. We recommend following the manual process for [Nethermind](../../../new-validator-process-flow/nethermind-node-setup.md) or [OpenEtherum](../../../new-validator-process-flow/openethereum-node-instructions.md) validator node deployment.
{% endhint %}

{% hint style="info" %}
If you experience any issues during installation, please post your questions in the [https://forum.poa.network/c/xdai-chain/validators-support-private](https://forum.poa.network/c/xdai-chain/validators-support-private). Also see the troubleshooting section at the end of this post.
{% endhint %}

## Install AWS CLI and Ansible Modules on Control Machine

1. check if you have aws cli installed

   ```bash
   aws --version
   ```

   if not - install it following [these instructions](http://docs.aws.amazon.com/cli/latest/userguide/installing.html). The simplest way is to use `pip`:

   ```bash
   pip install awscli --upgrade --user
   ```

   Mac systems with homebrew installed:

   ```bash
   brew install awscli
   ```

2. Also, use `pip` to install the following python packages required by ansible:

   ```bash
   sudo pip install boto
   sudo pip install boto3
   ```

## Configuring your AWS Account

1\) Register \(if you haven't already\) and login to the AWS management console: [https://aws.amazon.com/console/](https://aws.amazon.com/console/)

2\) Create CLI credentials: open IAM home [https://console.aws.amazon.com/iam/home](https://console.aws.amazon.com/iam/home), select "Users" on the left hand side navigation bar and then click "Add user". Pick a username, and check "Programmatic access" for "Access type". NOTE: For clarity we recommend using identical usernames on your Ansible Control Station and your remote node. For example, one can create a user named "ubuntu" on both your Ansible Control Station and your remote note.

3\) Click "Next: Permissions" - you can choose any of the available options, and "Attach existing policies directly" is the simplest one. In the list of policy types, search for and then check "AmazonEC2FullAccess". Click "Next:Review". Review your account and click "Create user" to proceed.

{% hint style="danger" %}
**Copy "Access Key ID" and "Secret Access Key" without leaving this page**, because there is no other way to retrieve "Secret Access Key" later and you will have to start again and create another user.
{% endhint %}

4\) After copying this important information, select **Close**.

5\) After you've copied and saved your AWS secret keys,  upload your SSH public key. In the top left corner of the page select **Services -&gt; EC2**. On the left sidebar select **Network & Security -&gt; Key Pairs**. Click **Import Key Pair.** Give a name to this keypair, otherwise the base name of the file will be used \(by default `id_rsa`\). Browse your Ansible Control Station file system for the public key.

6\) Configure aws cli:

```bash
aws configure
```

provide your credentials \(**Access Key ID** and **Secret Access Key**\) from earlier. Choose a region for your account \(e.g. `us-east-2`\) and output format \(`json` is recommended\).

7\) Check that the keypair was correctly imported:

```bash
aws ec2 describe-key-pairs
```

you should see your keypair name in the list.

8\) Choose available aws VPC and Subnet. Run this command to list subnets

```text
aws ec2 describe-subnets
```

select any subnet with `"State": "available"` and non-zero `AvailableIpAddressCount`. You need to note `SubnetId` and `VpcId` of this subnet for later use.

9\) Clone the repository with ansible playbooks and checkout branch corresponding to xDai:

```bash
git clone https://github.com/poanetwork/deployment-playbooks.git
cd deployment-playbooks
git checkout dai
```

10\) Go to the `aws` folder

```bash
cd aws
```

11\) Create configuration file

```bash
cp group_vars/all.yml.example group_vars/all.yml
```

12\) Edit this file in your favourite text editor \(e.g. `nano`\)

```bash
nano group_vars/all.yml
```

and provide the following configuration parameters:

```yaml
access_key: "your aws access key"
secret_key: "your aws secret key"

awskeypair_name: "aws keypair name"
region: "us-east-1" # you can choose a different region
vpc_id: "your VpcId"
vpc_subnet_id: "your SubnetId"
```

13\) run the playbook \(**run from the aws folder**\)

```bash
ansible-playbook validator.yml --private-key ~/.ssh/id_rsa
```

If the path to your private key is different, use that instead of `~/.ssh/id_rsa`. If successful, you should see a successful play recap.

14\) open **aws** console, go to **ec2 instances** and check that new instance is created, note it's IP address for later use.

15\) Next **you must run a second Ansible playbook** from the root directory to complete the setup - _instructions in process_

## Troubleshooting:

> \[WARNING\] provided hosts list is empty, only localhost is available. Note that the implicit localhost does not match 'all'.

Make sure you are in the aws subdirectory when running the playbook \(step 13\).

> Syntax error while loading YAML

Check that variables are tabbed properly

> \[ami-XXX\] does not exist.

ami is tied to the aws region your chose, ie east-region-2. To find the ami, go to the ec2 console at us-east-1 region, find the AMI tab and enter the current AMI. It will show you something similar to `ubuntu/images/hvm-ssd/ubuntu-xenial-16.04-amd64-server-20180205` which is the AMI name. Go to your region and enter the name at the same search string. Copy the AMI id from the output.

