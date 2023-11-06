```
nmcli connection show
sudo nmcli connection add con-name static-ens18 ifname ens18 type ethernet ip4 192.168.0.11/24 gw4 192.168.0.1
sudo nmcli connection up static-ens18
nmcli connection show
```
