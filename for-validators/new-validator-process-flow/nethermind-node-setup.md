---
description: Instructions for setting up a Nethermind Client Node
---

# Nethermind Node Setup

{% hint style="warning" %}
If you experience any issues during installation, post questions here: [https://forum.poa.network/c/xdai-chain/validators-support-private](https://forum.poa.network/c/xdai-chain/validators-support-private).
{% endhint %}

{% hint style="info" %}
**If you are migrating from a current OpenEthereum/Parity Node:** 

1. We recommend preparing through step 4 below \(update .env file\) on a clean instance, but **DO NOT launch \( do not proceed to step 5 `docker-compose up -d`\) until you have stopped your current instance**. 
2. Once your new node is prepared, stop your current OE/Parity instance
   1. If using docker, stop with `docker-compose down` 
   2. If using an ansible deploment playbook, uninstall with`sudo pip uninstall --yes ansible` or follow these instructions [https://howtoinstall.co/en/ubuntu/xenial/ansible?action=remove](https://howtoinstall.co/en/ubuntu/xenial/ansible?action=remove) 
3. Once you have confirmed your previous node is stopped, proceed with step 5 below and launch the new instance.  Initial sync should take about 15 minutes.
{% endhint %}

## Validator Node Specs

Nethermind can be supported by a variety of cloud-based providers. Instructions are available here for [UpCloud](https://docs.nethermind.io/nethermind/guides-and-helpers/cloud-providers/upcloud), which can be generalized to other providers. If you are already with a provider, we recommend launching a new, clean instance.

### Minimum specifications

* OS: Ubuntu,  Windows & MacOs. [See supported platforms ](https://docs.nethermind.io/nethermind/first-steps-with-nethermind/supported-platforms)
* CPU: minimum 2 cores
* RAM: minimum 4GB
* Disk: 50gb SSD
* Open network ports: SSH port \(default 22 TCP\), 30303 UDP/TCP. For security purposes, close other ports.
* Check that you have git installed `git --version`
  * if not, install it following instructions [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

{% hint style="info" %}
See the [Nethermind Docs](https://docs.nethermind.io/nethermind/) for additional information
{% endhint %}

## Node setup

Login to your node to begin.

**For basic docker instructions**, see the github repo at [https://github.com/xdaichain/validator-node-dockerized/tree/nethermind\#readme](https://github.com/xdaichain/validator-node-dockerized/tree/nethermind#readme
)

### 1\) Install Docker Engine & Docker Compose

Installation instructions will vary based on OS. Follow the instructions here:

* [https://docs.docker.com/get-docker/](https://docs.docker.com/get-docker/) 
* [https://docs.docker.com/compose/install/](https://docs.docker.com/compose/install/)

### 2\) Sync Clock

Your clock should by synchronized to prevent skipping block sealing.

 Enter`timedatectl status` , you should see similar output:

```bash
Local time: Tue 2020-06-30 17:16:19 UTC
Universal time: Tue 2020-06-30 17:16:19 UTC
RTC time: Tue 2020-06-30 17:16:19
Time zone: Etc/UTC (UTC, +0000)
System clock synchronized: yes
systemd-timesyncd.service active: yes
RTC in local TZ: no
```

If **`System clock synchronized`** displays **`yes`**   you are ready to go, proceed to step 3.

If not, you can either:

* [x] synchronize clock with NTP servers \(allow **UDP** port **123** for both incoming and outgoing traffic\) or
* [x] use the following script to sync with google.com:

Create `fixtime.sh` script and run it with `watch -n 60` command in a `screen`

```bash
echo sudo date -s '"$(wget -qSO- --max-redirect=0 google.com 2>&1 | grep Date: | cut -d' ' -f5-8)Z"' > fixtime.sh
chmod +x fixtime.sh
screen -S time
watch -n 60 ./fixtime.sh
```

Press `Ctrl+A+D` to leave the `screen`

### 3\) Clone the Repo

```bash
$ git clone -b nethermind https://github.com/xdaichain/validator-node-dockerized
$ cd validator-node-dockerized
```

### 4\) Update .env File

{% hint style="info" %}
You will need your private mining key to proceed \([see step 3 here to retrieve a key string using MetaMask](https://github.com/xdaichain/validator-node-dockerized/tree/nethermind#readme)\)
{% endhint %}

Copy `.env.example` to `.env` and configure the `.env` file. Define the following settings.

```text
ETHSTATS_ID=[validator_name]
ETHSTATS_CONTACT=[contact_email]
ETHSTATS_SECRET=[netstat_secret_key]
KEY=[your_private_key_for_mining_address]
SEQAPIKEY=[seq_api_key]
```

* `ETHSTATS_ID` - The displayed name of your validator in [Netstats](https://dai-netstat.poa.network/)
* `ETHSTATS_CONTACT` - Validator's contact \(e.g., e-mail\)
* `ETHSTATS_SECRET` - Secret key to connect to Netstat \([Available here ](https://forum.poa.network/t/netstats-server-info/2781)- request access to the forum to view - please keep it private\)
* `KEY` - Your mining address private key \(64 characters long **without leading `0x`**\)
* `SEQAPIKEY` - An API key for [Seq](https://datalust.co/seq) log collector \(should be provided by xDai team, please, request it\).

### 5\) Start the Node

```text
$ docker-compose up -d
```

Once docker containers are created, the node will sync with the chain \(may take a while\).

### 6\) Remove Private Key from .env File \(optional but recommended\)

After your docker container is created and started, it doesn't need the key anymore, so the key can be removed from `.env` for security reasons. **But note, that if you `down` your container, you will need to specify the key again before you `up` \(recreate\) the docker container.**

To restart, cd into the  `validator-node-dockerized` directory and use `docker-compose stop` then `docker-compose start`

### 7\) Check Logs

To check the logs and verify operations \(look for the `Sealed block` log\).

```text
docker-compose logs -f nethermind
```

## Become a POSDAO Candidate

Once the node is operational, proceed to [Becoming a Candidate instructions step 5](../../for-stakers/staking-protocol/become-a-candidate-validator.md#proceed-to-step-5-after-mining-node-is-configured-and-functional). Here you will access the staking DApp with your staking address in order to fund the mining node.

