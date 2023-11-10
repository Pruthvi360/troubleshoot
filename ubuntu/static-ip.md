```
sudo apt update
sudo apt install openvswitch-switch -y
sudo systemctl start openvswitch-switch
sudo systemctl enable openvswitch-switch
sudo systemctl status openvswitch-switch
```
```
sudo nano /etc/netplan/static.yaml
```
```
network:
  version: 2
  renderer: networkd
  ethernets:
    ens18:
      addresses:
        - 192.168.0.11/24
      nameservers:
        addresses:
          - 8.8.8.8
          - 8.8.4.4
      routes:
        - to: 0.0.0.0/0
          via: 192.168.0.1
          on-link: true
          table: 100
    ens19:
      addresses:
        - 192.168.0.12/24
      nameservers:
        addresses:
          - 8.8.8.8
          - 8.8.4.4
      routes:
        - to: 0.0.0.0/0
          via: 192.168.0.1
          on-link: true
          table: 101
```
```
chmod 600 /etc/netplan/static.yaml
sudo netplan apply
```
