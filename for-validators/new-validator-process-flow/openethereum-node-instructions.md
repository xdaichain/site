# OpenEthereum / Parity Node Setup

{% hint style="warning" %}
If you experience any issues during installation, post your questions in the [https://forum.poa.network/c/xdai-chain/validators-support-private](https://forum.poa.network/c/xdai-chain/validators-support-private).

Additional reference: [https://github.com/xdaichain/validator-node-dockerized\#readme](https://github.com/xdaichain/validator-node-dockerized#readme)
{% endhint %}

## Process

{% hint style="info" %}
To become a new validator, you will run a node using a mining address and connect to it with a separate staking address. For details, see the [Become a Candidate](../../for-stakers/staking-protocol/become-a-candidate-validator.md) instructions, and proceed to these instructions following step 4.
{% endhint %}

## Validator Node Specs

OpenEthereum can be supported by a variety of cloud-based providers. If you are already with a provider, we recommend launching a new, clean instance.

### Minimum specifications:

* OS: Ubuntu Linux 16.04 LTS with root or sudo-user access over ssh
* CPU: minimum 2 cores
* RAM: minimum 4GB
* Disk: 50gb SSD 
  * Open network ports: SSH port \(default 22 TCP\), 30303 UDP. For security purposes, close other ports
* Check that you have git installed `git --version`
  * if not, install it following instructions [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

## Node setup

Login to your node to begin.

For basic instructions, see the github repo at [https://github.com/xdaichain/validator-node-dockerized](https://github.com/xdaichain/validator-node-dockerized)

### 1\) Install Docker Engine & Docker Compose

Installation instructions will vary based on OS. Follow the instructions here:

* [https://docs.docker.com/get-docker/](https://docs.docker.com/get-docker/) 
* [https://docs.docker.com/compose/install/](https://docs.docker.com/compose/install/)

### 2\) Sync Clock

Your clock should be synchronized to prevent skipping block sealing.

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

If **`System clock synchronized`** displays **`yes`** you are ready to go, proceed to step 3.

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
$ git clone https://github.com/xdaichain/validator-node-dockerized
$ cd validator-node-dockerized
```

### 4\) Save Mining Address JSON Keystore file and Password

Generate an external \(0x\) address and name your JSON keystore file as `key` and save it in the `validator-node-dockerized` directory. Save the keystore password to a `password` file. 

You can use the [`eth-keygen-json`](https://www.npmjs.com/package/eth-keygen-json)  tool made by [Peppersec.com](https://peppersec.com/) to generate and save.

Example:

```text
npm i eth-keygen-json -g
Please enter the password to encrypt your new ethereum key [input is hidden]
Address: 0xADDRESS
Creating folder with your private key and json keystore.
```

Alternate generation methods:

* Generate a key with the following OpenEthereum's CLI command:

```text
openethereum account new --keys-path <path_to_save_json_keystore>
```

* Use the MEW CX Google Chrome extension or MyCrypto desktop application to generate a keystore file for an existing account.
  * [MEW keystore file directions](https://kb.myetherwallet.com/en/security-and-privacy/what-is-a-keystore-file/)
  * [MyCrypto instructions](https://support.mycrypto.com/)

### 4\) Update .env File

Copy `.env.example` to `.env` and configure the `.env` file. Define the following settings.

```text
ETHSTATS_ID=[validator_name]
ETHSTATS_CONTACT=[contact_email]
ETHSTATS_SECRET=[netstat_secret_key]
EXT_IP=[external_server_ip]
ACCOUNT=[mining_address]
```

* `ETHSTATS_ID` - The displayed name of your validator in [Netstat](https://dai-netstat.poa.network/)
* `ETHSTATS_CONTACT` - Validator's contact \(e.g., e-mail\)
* `ETHSTATS_SECRET` - Secret key to connect to Netstat \([Available here ](https://forum.poa.network/t/netstats-server-info/2781)- you will need access to the forum to view, please keep it private\)
* `EXT_IP` -  External IP address of the current server
* `ACCOUNT` - Your public mining address \(40 characters **including the** **leading `0x`**\)

### 5\) Start the Node & Netstat Service

```text
$ docker-compose up -d
```

Once docker containers are created, the node will sync with the chain \(this may take a while\).

To restart, cd into the `validator-node-dockerized` directory and use `docker-compose stop` then `docker-compose start`

### 6\) Check NetStats

Open [https://dai-netstat.poa.network](https://dai-netstat.poa.network) and check that your node appears on the list and has &gt;0 peers. Wait until it synchronizes with the rest of the blockchain \(block number and block hash should match the rest of the network\).

### 7\) Access Staking DApp

Once the node is operational, proceed to [Becoming a Candidate instructions step 5](../../for-stakers/staking-protocol/become-a-candidate-validator.md#proceed-to-step-5-after-mining-node-is-configured-and-functional). Here you will access the staking DApp using your staking address in order to fund the mining node.

