---
description: Instructions for setting up a Nethermind Client Node
---

# Nethermind Node Setup

{% hint style="warning" %}
If you experience any issues during installation, post your questions in the [https://forum.poa.network/c/xdai-chain/validators-support-private](https://forum.poa.network/c/xdai-chain/validators-support-private).
{% endhint %}

## Validator Node Specs

Nethermind can be supported by a variety of cloud-based providers. Instructions are available here for [UpCloud](https://docs.nethermind.io/nethermind/guides-and-helpers/cloud-providers/upcloud), which can be generalized to other providers. 

### Minimum specifications:

* OS: Ubuntu,  Windows & MacOs. [See supported platforms ](https://docs.nethermind.io/nethermind/first-steps-with-nethermind/supported-platforms)
* CPU: minimum 2 cores
* RAM: minimum 4GB
* Disk: SSD
* Open network ports: SSH port \(default 22 TCP\), 30303 UDP. For security purposes, close other ports
* Check that you have git installed `git --version`
  * if not - install it following instructions [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

{% hint style="info" %}
See the [Nethermind Docs](https://docs.nethermind.io/nethermind/) for additional information
{% endhint %}

## Node setup

Login to your node to begin. 

* For basic instructions, see the github repo at [https://github.com/xdaichain/validator-node-dockerized/tree/nethermind\#readme](https://github.com/xdaichain/validator-node-dockerized/tree/nethermind#readme
  )

### 1\) Install Docker Engine & Docker Compose

Installation instructions will vary based on OS. Follow the instructions here:

* [https://docs.docker.com/get-docker/](https://docs.docker.com/get-docker/) 
* [https://docs.docker.com/compose/install/](https://docs.docker.com/compose/install/)

### 2\) Sync Clock

Enter `timedatectl status` and you should see similar output:

```bash
Local time: Tue 2020-06-30 17:16:19 UTC
Universal time: Tue 2020-06-30 17:16:19 UTC
RTC time: Tue 2020-06-30 17:16:19
Time zone: Etc/UTC (UTC, +0000)
System clock synchronized: yes
systemd-timesyncd.service active: yes
RTC in local TZ: no
```

If `System clock synchronized` displays `yes` you are all set, otherwise either:

* [x] synchronize clock with NTP servers \(allow **UDP** port **123** for both incoming and outgoing traffic\)
* [x] use below script to sync with google.com:

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

### 4\) Update .env file

Copy `.env.example` to `.env` and configure the `.env` file.

```text
ETHSTATS_ID=[validator_name]
ETHSTATS_CONTACT=[contact_email]
ETHSTATS_SECRET=[netstat_secret_key]
KEY=[your_private_key_for_mining_address]
```

* `ETHSTATS_ID` - The displayed name of your validator in [Netstats](https://dai-netstat.poa.network/).
* `ETHSTATS_CONTACT` - Validator's contact \(e.g., e-mail\).
* `ETHSTATS_SECRET` - Secret key to connect to Netstat \([Available here ](https://forum.poa.network/t/netstats-server-info/2781)- you will need access to the forum to view, please keep it private\).
* `KEY` - Your mining address private key \(64 characters long **without leading `0x`**\).

### 5\) Start your node

```text
$ docker-compose up -d
```

Once docker containers are created, the node will sync with the chain \(may take a while\).

To restart, cd into the  `validator-node-dockerized` directory and use `docker-compose stop` then `docker-compose start`

To check the logs and verify operations \(look for the `Sealed block` log\).

```text
docker-compose logs -f nethermind-validator
```

![](https://gblobscdn.gitbook.com/assets%2F-LQf-hsMLYBdJYXFr5R0%2F-MB-EyG6yv363iG_CHEH%2F-MB-M2YpmaVRZVZXRJPS%2Fimage.png?alt=media&token=1bf89e64-b061-451d-9bb7-002830a35dc4)

