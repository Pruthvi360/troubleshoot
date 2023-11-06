```
nmcli connection show
sudo nmcli connection add con-name static-ens18 ifname ens18 type ethernet ip4 192.168.0.11/24 gw4 192.168.0.1
sudo nmcli connection up static-ens18
nmcli connection show
```
```
nmcli connection edit static-ens18
set ipv4.method manual
set ipv4.addresses 192.168.0.11/24
set ipv4.gateway 192.168.0.1
set ipv4.dns 8.8.8.8,8.8.4.4
save
quit
nmcli connection down static-ens18
nmcli connection up static-ens18
```
