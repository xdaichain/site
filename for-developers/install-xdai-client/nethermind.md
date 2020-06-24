# Nethermind

{% hint style="warning" %}
Nethermind Validator is currently running on POSDAO in Beta. A new release is expected in the near future:

Validator: [https://blockscout.com/poa/xdai/address/0x1A740616e96E07d86203707C1619d9871614922A/validations](https://blockscout.com/poa/xdai/address/0x1A740616e96E07d86203707C1619d9871614922A/validations) 

Ethstats: [https://dai-netstat.poa.network/](https://dai-netstat.poa.network/)
{% endhint %}

Nethermind Launcher is a self-contained app - you do not need to install .NET separately to run it. 

\*\*\*\*📄 **Nethermind Docs**: [https://nethermind.readthedocs.io/en/latest/](https://nethermind.readthedocs.io/en/latest/)

\*\*\*\*📦 **Latest Packages:** [http://downloads.nethermind.io/](http://downloads.nethermind.io/)

\*\*\*\*🛑 **To stop Nethermind:** `Control + c`

## **Configuration**

The Nethermind Launcher will present several options on start. Use arrow keys to select options. [See here for available CLI methods](https://nethermind.readthedocs.io/en/latest/cli.html) - CLI supports javascript.

{% hint style="info" %}
When you start the Launcher choose the following options to sync a node:

* Start Nethermind: **Node**
* Select network: **xDai** 
* Select sync: **Fast sync**
{% endhint %}

### **macOS**

1. Install dependencies: `brew install gmp && brew install snappy && brew install lz4`
2. Download mac package
3. Unzip the file
4. cd into the folder
5. ./Nethermind.Launcher
6. Select desired configuration

### **Windows**

1. Download windows package 
2. Unzip the file
3. run Nethermind.Launcher.exe
4. Select desired configuration

### **Linux** \(Ubuntu 16.04 or above\)

1\) Install dependencies: 

```text
sudo apt update && sudo apt install libsnappy-dev libc6-dev libc6 unzip
```

2\) Create a new user

```text
sudo useradd -m -s /bin/bash nethermind
```

3\) Increase the max number of open files

```text
sudo bash -c 'echo "nethermind soft nofile 1000000" > /etc/security/limits.d/nethermind.conf'
sudo bash -c 'echo "nethermind hard nofile 1000000" >> /etc/security/limits.d/nethermind.conf'
```

4\) Switch to the new user

```text
sudo su - nethermind
```

5\) Get Nethermind: download the latest Nethermind \(not NDM\) package \(list is here: [http://downloads.nethermind.io/](http://downloads.nethermind.io/)\) 

```text
wget [LINUX_PACKAGE_URL]
```

6\) Extract the files

```text
unzip [LINUX_PACKAGE_FILENAME] -d nethermind
```

7\) Switch directories

```text
cd nethermind
```

8\) Start the Nethermind Launcher 

```text
./Nethermind.Launcher
```

