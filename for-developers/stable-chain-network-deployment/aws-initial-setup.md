---
description: Prepare AWS for Node Deployment
---

# 2\) AWS Initial Setup

1\) Register \(if you haven't already\) and login to the AWS management console: [https://aws.amazon.com/console/](https://aws.amazon.com/console/)  


2\) To create credentials for the cli, open IAM home [https://console.aws.amazon.com/iam/home](https://console.aws.amazon.com/iam/home), select **Users** on the left navigation bar and click the **Add User** button. 

![](../../.gitbook/assets/add_user_1.png)

3\) Pick a username, check **Programmatic access** for **AWS access type**, and click the **Next: Permissions** button.

![](../../.gitbook/assets/user_2.png)

{% hint style="info" %}
For clarity we recommend using identical usernames on your Ansible Control Station and your remote node. For example,  create a user named "ubuntu" on both your Ansible Control Station and your remote note.
{% endhint %}

4\) Choose any of the available options - **Attach existing policies directly** is the simplest one. In the list of policy types, search for and select **AmazonEC2FullAccess**.  Click the **Next:Tags** button.

![](../../.gitbook/assets/policies.png)

5\) Enter any Tags \(optional\) and Click the **Next:Review** button. IAM tags are key-value pairs you can add to your user. Tags can include user information, such as an email address, or can be descriptive, such as a job title. 

![](../../.gitbook/assets/tags.png)

6\) Review your account and click the the **Create user** button to proceed.

![](../../.gitbook/assets/createuser.png)

7\) Save Keys. You can download a csv and/or save the keys in a text file. After copying this important information, select **Close**.

{% hint style="warning" %}
**It is very important that you copy Access Key ID and Secret Access Key without leaving this page**, because there is no other way to retrieve the **Secret Access Key** later and you will have to start again and create another user. 
{% endhint %}

![](../../.gitbook/assets/download-and-save-key.png)

8\) After you've copied and saved your AWS secret keys, you will upload your SSH public key. In the top left corner of the page select Services -&gt; EC2. On the left sidebar select Network & Security -&gt; **Key Pairs**. Click the **Import Key Pair** button.

![](../../.gitbook/assets/importkp1.png)

9\) Name this keypair, otherwise the base name of the file will be used \(by default `id_rsa`\). Browse your Ansible Control Station file system for the public key, or copy/paste:

```text
pbcopy < ~/.ssh/id_rsa.pub
```

This will copy your public key into your clipboard and can then be pasted.

![Enter a key pair name in step 1 if you don&apos;t want to use the base name. ](../../.gitbook/assets/import_2.png)

9\) Configure aws cli from your local machine:

```text
aws configure
```

Provide your credentials \(Access Key ID and Secret Access Key\) from earlier. Choose a region for your account \(e.g. `us-east-2`\) and output format \(`json` is recommended\).

10\) Check  the keypair was imported correctly:

```text
aws ec2 describe-key-pairs
```

you should see your keypair name in the list in JSON format.

{% hint style="success" %}
Next: [Download and Launch Playbooks](3-download-and-configure-playbook.md)
{% endhint %}



