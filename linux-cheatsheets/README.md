```
useradd -s /bin/bash -m -d /home/ansibleadmin ansibleadmin
```
```
passwd 1996
```
```
usermod -aG sudo ansibleadmin
```
```
nano /etc/sudoers
```
```
ansibleadmin ALL=(ALL)    NOPASSD:ALL
```
