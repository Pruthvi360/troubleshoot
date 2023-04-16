## Run this below 3 commands in centos 8 this will fix the problem

sudo yum clean all
sudo yum clean metadata
dnf clean all

## start with the installation

yum install jenkins -y
