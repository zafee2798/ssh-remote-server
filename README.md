# SSH Remote Server Setup
Project URL: https://roadmap.sh/projects/ssh-remote-server-setup


This is a solution to the SSH Remote Server Setup project from roadmap.sh.

## Goal

Set up a remote Linux server and configure it to allow SSH connections
using two separate SSH key pairs.

## What was done

1. Provisioned a remote Linux server — an Ubuntu 24.04 LTS droplet on DigitalOcean.
2. Generated two separate SSH key pairs on the local machine:ssh-keygen -t ed25519 -C "my-first-key" -f ~/.ssh/id_ed25519
ssh-keygen -t ed25519 -C "my-second-key" -f ~/.ssh/id_ed25519_key2
3. Added the first public key to the server during droplet creation.
4. Added the second public key to the server's ~/.ssh/authorized_keys file
   after connecting with the first key.
5. Verified both keys work independently by connecting with each one.

## Connecting to the server

Using the first key:ssh -i ~/.ssh/id_ed25519 root@206.81.9.66
Using the second key:ssh -i ~/.ssh/id_ed25519_key2 root@206.81.9.66
Both commands successfully log in without a password, confirming both
key pairs are correctly authorized on the server.
