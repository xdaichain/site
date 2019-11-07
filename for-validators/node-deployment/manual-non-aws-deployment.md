---
description: Manually with your favorite hosting provider (AWS/Azure/OVH/etc)
---

# Manual \(Non-AWS\) Deployment

## Node requirements

Log into your Cloud Dashboard and deploy a new node with the following minimal system requirements:

* OS: Ubuntu Linux 16.04 LTS with root or sudo-user access over ssh
* CPU: minimum 2 cores
* RAM: minimum 4GB
* Disk: SSD
* Open network ports: SSH port \(default 22 TCP\), 30303 UDP. For security purposes, close other ports

If prompted to create new user during deployment - do so and skip the section about adding new user below. This guide will be using `ubuntu` as the username, use the default or replace with your `sudo` -user username.

## Add User with Sudo Privileges

1\) SSH into your node using the root password provided by cloud service \(either by web portal or email\) or using the SSH key supplied during deployment. If you already have  `sudo`  user, replace  `root`  with your user and skip the next two steps.

{% hint style="info" %}
Azure users will not have access to their root account by default, use your sudo user and skip to next section after connecting.
{% endhint %}

```text
ssh root@192.0.2.1
```

2\) Logged in as  `root`  add user and grant sudo privileges. It is recommended to use default user  `ubuntu`.

```text
adduser ubuntu
```

{% hint style="warning" %}
Enter a **STRONG** password to protect the user and you can leave the next 5 fields blank. Confirm the information is correct. We will ask for the`sudo` password during ansible deployment.
{% endhint %}

3\) Grant user `ubuntu` sudo privileges.

```text
usermod -aG sudo ubuntu
```

4\) [Return to Ansible Playbook Configuration in Phase 3 setup.](../new-validator-process-flow/new-xdai-validator-node-setup.md#iii-ansible-playbook-configuration)

