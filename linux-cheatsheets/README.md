# User adding to Ansible Server
```
useradd -s /bin/bash -m -d /home/ansibleadmin ansibleadmin
passwd 1996
usermod -aG sudo ansibleadmin
nano /etc/sudoers
ansibleadmin ALL=(ALL)    NOPASSWD:ALL
```
# Mapping Long Commands to shorter Commands
```
cd ~ & nano .bash_profile
alias latest='ls -lrt | tail -1'
source .bash_profile
alias
```
# Enabling SSH
```
nano /etc/ssh/sshd_config
PasswordAuthentication yes
systemctl restart sshd
```
# Authorized Keys
```
ssh-keygen
cd ~ & cd .ssh
nano authorized_keys
```
