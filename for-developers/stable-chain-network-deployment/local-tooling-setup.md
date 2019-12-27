# 1\) Local Tooling Setup

### 1. git

1. check that you have git installed

```text
git --version
```

if not - install it following instructions [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

### 2. python & pip

1\) check that you have python 2 version &gt;= 2.6.5 or python 3 version &gt;= 3.3 installed

```text
python --version
```

if not - install it choosing appropriate binary from [here](https://www.python.org/downloads/)

2\) check if you have `pip` python package manager install

```text
pip --version
```

if not - install it following instructions from [here](https://pip.pypa.io/en/stable/installing/). Basically, you need to download this script and save it on your computer [https://bootstrap.pypa.io/get-pip.py](https://bootstrap.pypa.io/get-pip.py) then run

```text
python get-pip.py
```

### 3. ansible

1\) follow [this guide](http://docs.ansible.com/ansible/latest/intro_installation.html) to install ansible. For example, you can use `pip` to do it:

```text
sudo pip install ansible
```

2\) use `pip` to install the following packages:

```text
sudo pip install boto
sudo pip install boto3
```

### 4. SSH keys

1. check if you already have a keypair:

```text
ls -la ~/.ssh
```

if you get error that directory does not exist or the directory is empty, you need to follow the instructions below. If you already have key pair, you can skip this section.

**Generate ssh key-pair**

```text
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

insert your email address there and a strong password. By default, keys will be saved to `~/.ssh/` and named `id_rsa` with your public key being `~/.ssh/id_rsa.pub`.

### 5. aws cli

1. check if you have aws cli installed

```text
aws --version
```

if not - install it following [these instructions](http://docs.aws.amazon.com/cli/latest/userguide/installing.html). The simplest way is to use `pip`:

```text
pip install awscli --upgrade --user
```

Mac systems with homebrew installed:

```text
brew install awscli
```

{% hint style="success" %}
Next: [AWS Initial Setup](aws-initial-setup.md)
{% endhint %}

