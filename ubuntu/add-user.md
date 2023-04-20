## Add user
```
useradd $USERNAME
```
## Change to sudo user and change to bin/bash shell
```
usermod -aG sudo $USERNAME
usermod -s /bin/bash $USERNAME
```
## Password
```
passwd $USERNAME
```
