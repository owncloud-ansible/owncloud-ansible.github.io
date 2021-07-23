---
title: Setup
---

These docs are work in progress so they will be incomplete.

{{< toc >}}

## Installing Ansible

### General

The current required Ansible min version is 2.10 on all Linux distribution. To install latest Ansible version with PIP use:

```Shell
python3 -m venv ~/ansible
source ~/ansible/bin/activate
pip3 install wheel ansible
```

### Ubuntu PPA

On Ubuntu you can also use a PPA to install Ansible 2.10.

```Shell
apt update
apt install software-properties-common
add-apt-repository ppa:ansible/ansible
apt update
apt install ansible
```

## Downloading the playground example playbooks

Download the playground repository which contains example playbooks (git needs to be installed).

```Shell
git clone https://github.com/owncloud-ansible/playground
cd playground
```

## Preparing the Ansible environment

### Collections

With Ansible 2.10 certain modules have be installed specifically using `ansible-galaxy` if use the package `ansible-base` instead of `ansible`. If you aim to run the playground example inventory using all ownCloud provided roles from our [Ansible GitHub Organization](https://github.com/owncloud-ansible) these collections are required:

```Shell
ansible-galaxy collection install community.mysql
ansible-galaxy collection install community.general
ansible-galaxy collection install ansible.posix
```

You can double check the installed Ansible collections:

```Shell
ansible-galaxy collection list

# /home/user/.ansible/collections/ansible_collections
Collection        Version
----------------- -------
ansible.posix     1.2.0
community.general 3.2.0
community.mysql   2.1.0
```

### Roles

You need to install a local copy of all the roles being used in the example playbook. To do so run the following command:

```Shell
ansible-galaxy install -r roles/requirements.yml
```

## Special requirements for playbook run

On some Linux distributions certain binaries need to be available for the playbook run on the target host.

### CentOS 7

These are the packages / repositories that need to be enabled / installed before the first playbook execution.

- Software Collections enabled:
  `yum install centos-release-scl`
- EPEL enabled:
  `yum install epel-release`
- GCC installed:
  `yum install gcc`
