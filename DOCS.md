# Ansible Tutorial

## 1. SSH Overview and Setup

OpenSSh ins a requirement for Ansible. OpenSSH is installed on the workstation and servers

OpenSSH should be in the workstation and servers

Create SSH Keypairs -

ssh-keygen -t ed25519 `-t` - represents the keytype. The ed25519 is a shorter keylength than the default

`-C` command - represents metadata or comment.

Example ssh-keygen =t ed25519 -C "my default"

### Adding SSH Keys to a server

`ssh-copy-id -i <~/.ssh/id_ed25519.pub> <ip_address_of_server>` -i (input file), location of private key

## 2. Install Ansible

Install from ubuntu repository

`sudo apt update && sudo apt install ansible`

Inventory File - Contaiins the list of IP addresses that we want to manage
Can contain IP address of domain name

Test ansible on all hosts:
`ansible all --key-file <location of ansible file> -i <host file> -m ping`

Create an ansible config file

The ansible config file is read by ansible on startup
Add the inventory file and private key file location for ansible

The new ansible.cfg file overides the default ansible.cfg file in /etc/ansible

Therefore new test command `ansible all -m ping`
