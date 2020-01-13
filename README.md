## Overview

Ansible playbook to deploy [Jenkins](https://jenkins.io/) server on AWS EC2

## Setup

1. Enter empty variables in `vars/vars.yml`
1. Add your ssh public key(s) to `vars/ssh_keys/authorized_keys.yml`

## Run

```
ansible-playbook --ask-vault-pass -i hosts --key-file "~/location/of/aws/<keypair>.pem" main.yml
```

## Dependencies

#### [Ansible](https://www.ansible.com/)

```
sudo easy_install pip
sudo pip install ansible
sudo mkdir /etc/ansible
sudo touch /etc/ansible/hosts
sudo touch /etc/ansible/ansible.cfg
```

## Using [Ansible Vault](https://docs.ansible.com/ansible/latest/user_guide/vault.html)

Make sure to encrypt any passwords/secrets with ansible vault:

* **Creating encrypted files:** `ansible-vault create file.yml`
* **Editing encrypted files:** `ansible-vault edit file.yml`
* **Encrypting files:** `ansible-vault encrypt file1.yml file2.yml file3.yml`
* **Decrypting files:** `ansible-vault decrypt file.yml`
