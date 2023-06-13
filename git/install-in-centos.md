## Generating SSH Key on client
[root@node2 ~]# 
```
ssh-keygen -C "dev@gmail.com"
```
Generating public/private rsa key pair.
Enter file in which to save the key (/root/.ssh/id_rsa): /root/.ssh/id_dev_rsa
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /root/.ssh/id_dev_rsa.
Your public key has been saved in /root/.ssh/id_dev_rsa.pub.
The key fingerprint is:
SHA256:oXUbsjEhDw8syKeJ/MG2MYaAwtzf/psmSyYrIyl4bbI dev@gmail.com
The key's randomart image is:
+---[RSA 2048]----+
|+... .+ .        |
|+oo.o .* .       |
|+.o+... O o      |
|.ooB . + B o     |
|  + = o S .      |
|   o   .         |
|. .. . o.        |
|ooooo =. o.      |
|..E+o. .+o.      |
+----[SHA256]-----+
! Installing Git on CentOS Server
 [root@master-node ~]#
```
yum install -y git
```
! Add user git on Server
[root@master-node ~]# 
```
useradd gi
```
 ! Change password for user git
[root@master-node ~]# 
```
passwd git
```
Changing password for user git.
```
New password:
Retype new password:
```
passwd: all authentication tokens updated successfully.

! Create authorized_keys file under .ssh directory


[root@master-node ~]# 
```
su git
```
Password:
[git@master-node ~]# 
```
mkdir ~/.ssh && touch ~/.ssh/authorized_keys
```

! Copy Public key On Client machine to remote server
[root@node2 ~]# 
```
cat .ssh/id_dev_rsa.pub | ssh root@172.16.102.131 "cat >>
  /home/git/.ssh/authorized_keys"
```  
```
Command                            Description

git config --global user.name     "firstname lastname" Sets up a name that appears in the version history

git config --global user.email    "email-address" Sets up an email address that will be associated with each history marker

git init                           Initializes an existing directory as a Git repository
```
