# Setting up an SSH Server and Key Exchange on a **Server**

This guide explains how to install and configure an SSH server on **Server**, then generate an SSH key and transfer it from the **Computer** in order to establish a secure passwordless connection.

## Requirement
the **Server** run on a linux environnement and you can run it as a root.

The **Computer** need to have a linux terminal. From a Windows, you have two possibility : 
- Run a linux system environnement via a dual boot ([Debian](https://www.debian.org/distrib), [Unbuntu](https://ubuntu.com/download), etc..)
- Run a linux terminal via [WSL](https://learn.microsoft.com/en-us/windows/wsl/install)

The **Computer** is on the same network as the **Server** or can communicate with him.

## 1. Install the SSH server on the **Server**

```bash
# Update packages
sudo apt update

# Install OpenSSH Server
sudo apt install openssh-server

# Check that the SSH service is running
sudo systemctl status ssh
```
If the service is not active, start it with:  ``` sudo systemctl enable ssh --now ```

# Check IP of the server
```bash
ip a
```
> Note the IP address (example: 192.168.1.42). This is the address Computer will use to connect.
## 2. First test of the SSH-connection
To test the ssh server on your **Server**, you can firstly try to connect to it.
```bash
# Replace "username" with the actual username on the Server
# replace "SERVER_IP" with the IP address of the server
ssh username@SERVER_IP
# It will ask you the passwork 
```

## 3. Generate an SSH key on the **Computer**

```bash
# generation of the SSH key
# Replace "username" with the actual username the Computer
# replace "SERVER_IP" with the IP address of the Computer
ssh-keygen -t ed25519 -C "username@computer"
```
Press Enter to accept the default location (~/.ssh/id_ed25519).

> You can also set a passphrase for extra security if desired.


## 4. Transfer the public key to the server
From the Computer :
```bash
# Replace "username" with the actual username on the Server
# replace "SERVER_IP" with the IP address of the server
ssh-copy-id username@Server_IP
```
Enter the password for the user on Server one last time.

> The key will be copied into ~/.ssh/authorized_keys on the server

## 5. Test the SSH connection

From the computer, run:
```bash
ssh username@COMPUTER_B_IP
```
You should now be connected without having to enter a password.

## 6. Additional security

On the **Server**, you can harden the SSH configuration:
```bash
sudo nano /etc/ssh/sshd_config
```
Disable password authentication:
```nginx
PasswordAuthentication no
```
Restart SSH:
```bash
sudo systemctl restart ssh
```